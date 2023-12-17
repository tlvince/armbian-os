<p align="center">
  <a href="#build-framework">
   <img src="https://raw.githubusercontent.com/armbian/build/master/.github/armbian-logo.png" alt="Armbian logo" width="144">
  </a><br>
  <strong>Armbian OS</strong><br>
<br>
<a href=https://github.com/armbian/os/actions/workflows/complete-artifact-matrix-all.yml><img alt="GitHub Workflow Status" src="https://img.shields.io/github/actions/workflow/status/armbian/os/complete-artifact-matrix-all.yml?logo=githubactions&label=Artifacts%20make&style=for-the-badge&branch=main"></a>
<a href=https://github.com/armbian/os/actions/workflows/repository-update.yml><img alt="GitHub Workflow Status" src="https://img.shields.io/github/actions/workflow/status/armbian/os/repository-update.yml?logo=githubactions&label=Repository%20update&style=for-the-badge&branch=main"></a>
<a href=https://github.com/armbian/os#latest-smoke-tests-results><img alt="GitHub Workflow Status" src="https://img.shields.io/github/actions/workflow/status/armbian/os/smoke-tests.yml?logo=githubactions&label=Smoke%20tests&style=for-the-badge&branch=main"></a>
</p>


# What does this project do?

- Keeps build framework [packages artifacts](https://github.com/orgs/armbian/packages) cache up to date
- Keeps stable [apt.armbian.com](https://apt.armbian.com) and nightly [beta.armbian.com](https://beta.armbian.com) packages repository up to date
- Builds [nightly](https://github.com/armbian/os/releases) and [stable images](https://www.armbian.com/download/) and uploads them to Armbian CDN
- Keep synchronizing the selection of [3rd party](external) applications with Armbian repositories
- Tests install of all packages added onto stable and testing Debian and Ubuntu releases

# How to enable images?

If you want to enable build configurations, edit [yaml config files](userpatches) and send a pull request. ([example](https://github.com/armbian/os/commit/70f3be4f3d96e9a301be751d3ecf3a24394356f9) )

# When is this happening?

- Artifacts cache is updated every eight hours, starting at 0:00 AM UTC
- Repository update starts after **artifacts cache update** is done succesfully.
- Smoke tests starts **manually**.
- Nightly images are build once per day, at 2:00 AM UTC, or if [build config is changed](https://github.com/armbian/os/blob/main/userpatches/targets-release-nightly.yaml)
- Manually, when Armbian [release manager](https://github.com/orgs/armbian/teams/release-manager) executes a build action

# Latest smoke tests results:

- installs **kernels**, **device tree blob** and **headers**
- runs **network** (iperf) and **computing performance** tests (7z benchmark)
- store **armbianmonitor** logs

<!--START_SECTION:data-section-->
<table width="100%"><tr><td align="left"><a id=Board ID href=#Board ID><b>Board name</b></a></td><td align=center><b>Kernel version</b></td><td align=center><b>Support</b></td><td align=left><b>Logs</b></td><td align=right><b>Iperf</b></td><td align=right><b>7z -b</b></td><td align=right><b>Repo</b></td></tr><tr><td align="left"><a id=khadas-vim1 href=#khadas-vim1>Khadas VIM1</a></td><td align=center>6.1.68-current-meson64</td><td align=center><a href=#khadas-vim1><img src=https://img.shields.io/static/v1?label=&message=Standard&color=green></a></td><td align=left><a href=https://paste.armbian.com/uyegetubah><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>98</td><td align=right>3720</td><td align=right>beta</td></tr><tr><td align="left"><a id=khadas-vim1 href=#khadas-vim1>Khadas VIM1</a></td><td align=center>6.6.7-edge-meson64</td><td align=center><a href=#khadas-vim1><img src=https://img.shields.io/static/v1?label=&message=Standard&color=green></a></td><td align=left><a href=https://paste.armbian.com/ananemolix><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>90</td><td align=right>3707</td><td align=right>beta</td></tr><tr><td align="left"><a id=pineh64 href=#pineh64>Pine H64</a></td><td align=center>6.1.68-current-sunxi64</td><td align=center><a href=https://www.armbian.com/donate/><img src=https://img.shields.io/static/v1?label=&message=Community&color=white></a></td><td align=left><a href=https://paste.armbian.com/eqabevikiv><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>949</td><td align=right>4258</td><td align=right>beta</td></tr><tr><td align="left"><a id=pineh64 href=#pineh64>Pine H64</a></td><td align=center>6.6.7-edge-sunxi64</td><td align=center><a href=https://www.armbian.com/donate/><img src=https://img.shields.io/static/v1?label=&message=Community&color=white></a></td><td align=left><a href=https://paste.armbian.com/ujawuwuwit><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>947</td><td align=right>4220</td><td align=right>beta</td></tr><tr><td align="left"><a id=zeropi href=#zeropi>ZeroPi</a></td><td align=center>5.15.143-legacy-sunxi</td><td align=center><a href=https://www.armbian.com/donate/><img src=https://img.shields.io/static/v1?label=&message=Community&color=white></a></td><td align=left><a href=https://paste.armbian.com/wefifobuna><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>579</td><td align=right>2653</td><td align=right>beta</td></tr><tr><td align="left"><a id=orangepiprime href=#orangepiprime>Orange Pi Prime</a></td><td align=center>n/a</td><td align=center><a href=#orangepiprime><img src=https://img.shields.io/static/v1?label=&message=Standard&color=green></a></td><td align=left><img src=https://img.shields.io/static/v1?label=&message=n/a&color=white></td><td align=right>n/a</td><td align=right>n/a</td><td align=right></td></tr><tr><td align="left"><a id=bananapim2ultra href=#bananapim2ultra>Banana Pi M2 Ultra</a></td><td align=center>n/a</td><td align=center><a href=https://www.armbian.com/donate/><img src=https://img.shields.io/static/v1?label=&message=Community&color=white></a></td><td align=left><img src=https://img.shields.io/static/v1?label=&message=n/a&color=white></td><td align=right>n/a</td><td align=right>n/a</td><td align=right></td></tr><tr><td align="left"><a id=tinkerboard-2 href=#tinkerboard-2>Tinker Board 2</a></td><td align=center>6.1.68-current-rockchip64</td><td align=center><a href=https://www.armbian.com/donate/><img src=https://img.shields.io/static/v1?label=&message=Community&color=white></a></td><td align=left><a href=https://paste.armbian.com/cunalitalo><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>880</td><td align=right>6803</td><td align=right>beta</td></tr><tr><td align="left"><a id=lepotato href=#lepotato>Le potato</a></td><td align=center>6.1.68-current-meson64</td><td align=center><a href=#lepotato><img src=https://img.shields.io/static/v1?label=&message=Standard&color=green></a></td><td align=left><a href=https://paste.armbian.com/zaguvamude><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>89</td><td align=right>3773</td><td align=right>beta</td></tr><tr><td align="left"><a id=lepotato href=#lepotato>Le potato</a></td><td align=center>6.6.7-edge-meson64</td><td align=center><a href=#lepotato><img src=https://img.shields.io/static/v1?label=&message=Standard&color=green></a></td><td align=left><a href=https://paste.armbian.com/ifogilikap><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>89</td><td align=right>3787</td><td align=right>beta</td></tr><tr><td align="left"><a id=orangepi5 href=#orangepi5>Orange Pi 5</a></td><td align=center>5.10.160-legacy-rk35xx</td><td align=center><a href=#orangepi5><img src=https://img.shields.io/static/v1?label=&message=Standard&color=green></a></td><td align=left><a href=https://paste.armbian.com/avilayivos><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>890</td><td align=right>15705</td><td align=right>beta</td></tr><tr><td align="left"><a id=tinkerboard href=#tinkerboard>Tinker Board</a></td><td align=center>n/a</td><td align=center><a href=#tinkerboard><img src=https://img.shields.io/static/v1?label=&message=Standard&color=green></a></td><td align=left><img src=https://img.shields.io/static/v1?label=&message=n/a&color=white></td><td align=right>n/a</td><td align=right>n/a</td><td align=right></td></tr><tr><td align="left"><a id=orangepizero href=#orangepizero>Orange Pi Zero</a></td><td align=center>6.1.68-current-sunxi</td><td align=center><a href=#orangepizero><img src=https://img.shields.io/static/v1?label=&message=Standard&color=green></a></td><td align=left><a href=https://paste.armbian.com/ixavujuhus><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>90</td><td align=right>2521</td><td align=right>beta</td></tr><tr><td align="left"><a id=khadas-vim2 href=#khadas-vim2>Khadas VIM2</a></td><td align=center>n/a</td><td align=center><a href=#khadas-vim2><img src=https://img.shields.io/static/v1?label=&message=Standard&color=green></a></td><td align=left><img src=https://img.shields.io/static/v1?label=&message=n/a&color=white></td><td align=right>n/a</td><td align=right>n/a</td><td align=right></td></tr><tr><td align="left"><a id=khadas-vim2 href=#khadas-vim2>Khadas VIM2</a></td><td align=center>n/a</td><td align=center><a href=#khadas-vim2><img src=https://img.shields.io/static/v1?label=&message=Standard&color=green></a></td><td align=left><img src=https://img.shields.io/static/v1?label=&message=n/a&color=white></td><td align=right>n/a</td><td align=right>n/a</td><td align=right></td></tr><tr><td align="left"><a id=orangepizero2 href=#orangepizero2>Orange Pi Zero2</a></td><td align=center>6.1.68-current-sunxi64</td><td align=center><a href=#orangepizero2><img src=https://img.shields.io/static/v1?label=&message=Standard&color=green></a></td><td align=left><a href=https://paste.armbian.com/rejociqaxo><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>836</td><td align=right>3150</td><td align=right>beta</td></tr><tr><td align="left"><a id=orangepizero2 href=#orangepizero2>Orange Pi Zero2</a></td><td align=center>6.6.7-edge-sunxi64</td><td align=center><a href=#orangepizero2><img src=https://img.shields.io/static/v1?label=&message=Standard&color=green></a></td><td align=left><a href=https://paste.armbian.com/xusomakevo><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>840</td><td align=right>3084</td><td align=right>beta</td></tr><tr><td align="left"><a id=bananapim2pro href=#bananapim2pro>Banana Pi M2Pro</a></td><td align=center>n/a</td><td align=center><a href=#bananapim2pro><img src=https://img.shields.io/static/v1?label=&message=Standard&color=green></a></td><td align=left><img src=https://img.shields.io/static/v1?label=&message=n/a&color=white></td><td align=right>n/a</td><td align=right>n/a</td><td align=right></td></tr><tr><td align="left"><a id=bananapim2pro href=#bananapim2pro>Banana Pi M2Pro</a></td><td align=center>n/a</td><td align=center><a href=#bananapim2pro><img src=https://img.shields.io/static/v1?label=&message=Standard&color=green></a></td><td align=left><img src=https://img.shields.io/static/v1?label=&message=n/a&color=white></td><td align=right>n/a</td><td align=right>n/a</td><td align=right></td></tr><tr><td align="left"><a id=khadas-vim3 href=#khadas-vim3>Khadas VIM3</a></td><td align=center>n/a</td><td align=center><a href=#khadas-vim3><img src=https://img.shields.io/static/v1?label=&message=Standard&color=green></a></td><td align=left><img src=https://img.shields.io/static/v1?label=&message=n/a&color=white></td><td align=right>n/a</td><td align=right>n/a</td><td align=right></td></tr><tr><td align="left"><a id=khadas-vim3 href=#khadas-vim3>Khadas VIM3</a></td><td align=center>n/a</td><td align=center><a href=#khadas-vim3><img src=https://img.shields.io/static/v1?label=&message=Standard&color=green></a></td><td align=left><img src=https://img.shields.io/static/v1?label=&message=n/a&color=white></td><td align=right>n/a</td><td align=right>n/a</td><td align=right></td></tr><tr><td align="left"><a id=tanix-tx6 href=#tanix-tx6>Tanix TX6</a></td><td align=center>6.1.68-current-sunxi64</td><td align=center><a href=https://www.armbian.com/donate/><img src=https://img.shields.io/static/v1?label=&message=Community&color=white></a></td><td align=left><a href=https://paste.armbian.com/quduqanida><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>89</td><td align=right>4270</td><td align=right>beta</td></tr><tr><td align="left"><a id=tanix-tx6 href=#tanix-tx6>Tanix TX6</a></td><td align=center>6.6.7-edge-sunxi64</td><td align=center><a href=https://www.armbian.com/donate/><img src=https://img.shields.io/static/v1?label=&message=Community&color=white></a></td><td align=left><a href=https://paste.armbian.com/iwafezedav><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>89</td><td align=right>4161</td><td align=right>beta</td></tr><tr><td align="left"><a id=orangepioneplus href=#orangepioneplus>Orange Pi One+</a></td><td align=center>n/a</td><td align=center><a href=https://www.armbian.com/donate/><img src=https://img.shields.io/static/v1?label=&message=Community&color=white></a></td><td align=left><img src=https://img.shields.io/static/v1?label=&message=n/a&color=white></td><td align=right>n/a</td><td align=right>n/a</td><td align=right></td></tr><tr><td align="left"><a id=nanopim4 href=#nanopim4>NanoPi M4</a></td><td align=center>n/a</td><td align=center><a href=https://www.armbian.com/donate/><img src=https://img.shields.io/static/v1?label=&message=Community&color=white></a></td><td align=left><img src=https://img.shields.io/static/v1?label=&message=n/a&color=white></td><td align=right>n/a</td><td align=right>n/a</td><td align=right></td></tr><tr><td align="left"><a id=nanopim4 href=#nanopim4>NanoPi M4</a></td><td align=center>n/a</td><td align=center><a href=https://www.armbian.com/donate/><img src=https://img.shields.io/static/v1?label=&message=Community&color=white></a></td><td align=left><img src=https://img.shields.io/static/v1?label=&message=n/a&color=white></td><td align=right>n/a</td><td align=right>n/a</td><td align=right></td></tr><tr><td align="left"><a id=khadas-vim4 href=#khadas-vim4>Khadas VIM4</a></td><td align=center>n/a</td><td align=center><a href=#khadas-vim4><img src=https://img.shields.io/static/v1?label=&message=Standard&color=green></a></td><td align=left><img src=https://img.shields.io/static/v1?label=&message=n/a&color=white></td><td align=right>n/a</td><td align=right>n/a</td><td align=right></td></tr><tr><td align="left"><a id=uefi-x86 href=#uefi-x86>UEFI x86</a></td><td align=center>n/a</td><td align=center><a href=#uefi-x86><img src=https://img.shields.io/static/v1?label=&message=Standard&color=green></a></td><td align=left><img src=https://img.shields.io/static/v1?label=&message=n/a&color=white></td><td align=right>n/a</td><td align=right>n/a</td><td align=right></td></tr><tr><td align="left"><a id=uefi-x86 href=#uefi-x86>UEFI x86</a></td><td align=center>n/a</td><td align=center><a href=#uefi-x86><img src=https://img.shields.io/static/v1?label=&message=Standard&color=green></a></td><td align=left><img src=https://img.shields.io/static/v1?label=&message=n/a&color=white></td><td align=right>n/a</td><td align=right>n/a</td><td align=right></td></tr><tr><td align="left"><a id=uefi-x86 href=#uefi-x86>UEFI x86</a></td><td align=center>n/a</td><td align=center><a href=#uefi-x86><img src=https://img.shields.io/static/v1?label=&message=Standard&color=green></a></td><td align=left><img src=https://img.shields.io/static/v1?label=&message=n/a&color=white></td><td align=right>n/a</td><td align=right>n/a</td><td align=right></td></tr><tr><td align="left"><a id=orangepiwin href=#orangepiwin>Orange Pi Win</a></td><td align=center>n/a</td><td align=center><a href=https://www.armbian.com/donate/><img src=https://img.shields.io/static/v1?label=&message=Community&color=white></a></td><td align=left><img src=https://img.shields.io/static/v1?label=&message=n/a&color=white></td><td align=right>n/a</td><td align=right>n/a</td><td align=right></td></tr><tr><td align="left"><a id=orangepiwin href=#orangepiwin>Orange Pi Win</a></td><td align=center>n/a</td><td align=center><a href=https://www.armbian.com/donate/><img src=https://img.shields.io/static/v1?label=&message=Community&color=white></a></td><td align=left><img src=https://img.shields.io/static/v1?label=&message=n/a&color=white></td><td align=right>n/a</td><td align=right>n/a</td><td align=right></td></tr><tr><td align="left"><a id=nanopineo3 href=#nanopineo3>NanoPi Neo 3</a></td><td align=center>6.1.68-current-rockchip64</td><td align=center><a href=https://www.armbian.com/donate/><img src=https://img.shields.io/static/v1?label=&message=Community&color=white></a></td><td align=left><a href=https://paste.armbian.com/edakozobow><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>960</td><td align=right>3197</td><td align=right>beta</td></tr><tr><td align="left"><a id=rockpro64 href=#rockpro64>RockPro 64</a></td><td align=center>n/a</td><td align=center><a href=#rockpro64><img src=https://img.shields.io/static/v1?label=&message=Standard&color=green></a></td><td align=left><img src=https://img.shields.io/static/v1?label=&message=n/a&color=white></td><td align=right>n/a</td><td align=right>n/a</td><td align=right></td></tr><tr><td align="left"><a id=odroidc4 href=#odroidc4>Odroid C4</a></td><td align=center>6.1.68-current-meson64</td><td align=center><a href=https://www.armbian.com/donate/><img src=https://img.shields.io/static/v1?label=&message=Community&color=white></a></td><td align=left><a href=https://paste.armbian.com/tonaheqazu><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>890</td><td align=right>5597</td><td align=right>beta</td></tr><tr><td align="left"><a id=odroidc4 href=#odroidc4>Odroid C4</a></td><td align=center>6.6.7-edge-meson64</td><td align=center><a href=https://www.armbian.com/donate/><img src=https://img.shields.io/static/v1?label=&message=Community&color=white></a></td><td align=left><a href=https://paste.armbian.com/osokolaxud><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>890</td><td align=right>5612</td><td align=right>beta</td></tr><tr><td align="left"><a id=odroidc2 href=#odroidc2>Odroid C2</a></td><td align=center>n/a</td><td align=center><a href=#odroidc2><img src=https://img.shields.io/static/v1?label=&message=Standard&color=green></a></td><td align=left><img src=https://img.shields.io/static/v1?label=&message=n/a&color=white></td><td align=right>n/a</td><td align=right>n/a</td><td align=right></td></tr><tr><td align="left"><a id=odroidc2 href=#odroidc2>Odroid C2</a></td><td align=center>n/a</td><td align=center><a href=#odroidc2><img src=https://img.shields.io/static/v1?label=&message=Standard&color=green></a></td><td align=left><img src=https://img.shields.io/static/v1?label=&message=n/a&color=white></td><td align=right>n/a</td><td align=right>n/a</td><td align=right></td></tr><tr><td align="left"><a id=rpi4b href=#rpi4b>Raspberry Pi 4</a></td><td align=center>5.15.92-legacy-bcm2711</td><td align=center><a href=#rpi4b><img src=https://img.shields.io/static/v1?label=&message=Standard&color=green></a></td><td align=left><a href=https://paste.armbian.com/imitifekoq><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>90</td><td align=right>2860</td><td align=right>beta</td></tr><tr><td align="left"><a id=rpi4b href=#rpi4b>Raspberry Pi 4</a></td><td align=center>6.1.68-current-bcm2711</td><td align=center><a href=#rpi4b><img src=https://img.shields.io/static/v1?label=&message=Standard&color=green></a></td><td align=left><a href=https://paste.armbian.com/anahimasuv><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>90</td><td align=right>2830</td><td align=right>beta</td></tr><tr><td align="left"><a id=rpi4b href=#rpi4b>Raspberry Pi 4</a></td><td align=center>6.7.0-rc5-edge-bcm2711</td><td align=center><a href=#rpi4b><img src=https://img.shields.io/static/v1?label=&message=Standard&color=green></a></td><td align=left><a href=https://paste.armbian.com/etogaqeyoz><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>90</td><td align=right>2942</td><td align=right>beta</td></tr><tr><td align="left"><a id=bigtreetech-cb1 href=#bigtreetech-cb1>BigTreeTech CB1</a></td><td align=center>n/a</td><td align=center><a href=#bigtreetech-cb1><img src=https://img.shields.io/static/v1?label=&message=Standard&color=green></a></td><td align=left><img src=https://img.shields.io/static/v1?label=&message=n/a&color=white></td><td align=right>n/a</td><td align=right>n/a</td><td align=right></td></tr><tr><td align="left"><a id=orangepi-r1plus-lts href=#orangepi-r1plus-lts>Orange Pi R1 Plus LTS</a></td><td align=center>6.1.68-current-rockchip64</td><td align=center><a href=#orangepi-r1plus-lts><img src=https://img.shields.io/static/v1?label=&message=Standard&color=green></a></td><td align=left><a href=https://paste.armbian.com/vesivofeze><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>748</td><td align=right>2252</td><td align=right>beta</td></tr><tr><td align="left"><a id=odroidn2 href=#odroidn2>Odroid N2</a></td><td align=center>6.1.68-current-meson64</td><td align=center><a href=https://www.armbian.com/donate/><img src=https://img.shields.io/static/v1?label=&message=Community&color=white></a></td><td align=left><a href=https://paste.armbian.com/ipulacutic><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>889</td><td align=right>8850</td><td align=right>beta</td></tr><tr><td align="left"><a id=odroidn2 href=#odroidn2>Odroid N2</a></td><td align=center>6.6.7-edge-meson64</td><td align=center><a href=https://www.armbian.com/donate/><img src=https://img.shields.io/static/v1?label=&message=Community&color=white></a></td><td align=left><a href=https://paste.armbian.com/amasomevak><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>960</td><td align=right>8729</td><td align=right>beta</td></tr><tr><td align="left"><a id=orangepi5-plus href=#orangepi5-plus>Orange Pi 5 Plus</a></td><td align=center>n/a</td><td align=center><a href=#orangepi5-plus><img src=https://img.shields.io/static/v1?label=&message=Standard&color=green></a></td><td align=left><img src=https://img.shields.io/static/v1?label=&message=n/a&color=white></td><td align=right>n/a</td><td align=right>n/a</td><td align=right></td></tr><tr><td align="left"><a id=bananapicm4io href=#bananapicm4io>Banana Pi CM4IO</a></td><td align=center>6.4.13-edge-meson64</td><td align=center><a href=#bananapicm4io><img src=https://img.shields.io/static/v1?label=&message=Standard&color=green></a></td><td align=left><a href=https://paste.armbian.com/zijobomizu><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>890</td><td align=right>9450</td><td align=right>beta</td></tr><tr><td align="left"><a id=bananapicm4io href=#bananapicm4io>Banana Pi CM4IO</a></td><td align=center>6.4.13-edge-meson64</td><td align=center><a href=#bananapicm4io><img src=https://img.shields.io/static/v1?label=&message=Standard&color=green></a></td><td align=left><a href=https://paste.armbian.com/sovogenuro><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>880</td><td align=right>9315</td><td align=right>beta</td></tr><tr><td align="left"><a id=odroidm1 href=#odroidm1>Odroid M1</a></td><td align=center>6.6.4-edge-rk3568-odroid</td><td align=center><a href=https://www.armbian.com/donate/><img src=https://img.shields.io/static/v1?label=&message=Staging&color=orange></a></td><td align=left><a href=https://paste.armbian.com/jusojenoti><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>652</td><td align=right>5230</td><td align=right>beta</td></tr><tr><td align="left"><a id=odroidm1 href=#odroidm1>Odroid M1</a></td><td align=center>6.6.4-edge-rk3568-odroid</td><td align=center><a href=https://www.armbian.com/donate/><img src=https://img.shields.io/static/v1?label=&message=Staging&color=orange></a></td><td align=left><a href=https://paste.armbian.com/udeseginab><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>661</td><td align=right>5313</td><td align=right>beta</td></tr><tr><td align="left"><a id=nanopi-r4s href=#nanopi-r4s>NanoPi R4S</a></td><td align=center>6.1.68-current-rockchip64</td><td align=center><a href=#nanopi-r4s><img src=https://img.shields.io/static/v1?label=&message=Standard&color=green></a></td><td align=left><a href=https://paste.armbian.com/dahovisucu><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>960</td><td align=right>6447</td><td align=right>beta</td></tr><tr><td align="left"><a id=nanopi-r4s href=#nanopi-r4s>NanoPi R4S</a></td><td align=center>6.6.7-edge-rockchip64</td><td align=center><a href=#nanopi-r4s><img src=https://img.shields.io/static/v1?label=&message=Standard&color=green></a></td><td align=left><a href=https://paste.armbian.com/ikibewuyeb><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>889</td><td align=right>6571</td><td align=right>beta</td></tr><tr><td align="left"><a id=rpi4b href=#rpi4b>Raspberry Pi 4</a></td><td align=center>5.15.92-legacy-bcm2711</td><td align=center><a href=#rpi4b><img src=https://img.shields.io/static/v1?label=&message=Standard&color=green></a></td><td align=left><a href=https://paste.armbian.com/boqiyovoju><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>870</td><td align=right>5779</td><td align=right>beta</td></tr><tr><td align="left"><a id=rpi4b href=#rpi4b>Raspberry Pi 4</a></td><td align=center>6.1.68-current-bcm2711</td><td align=center><a href=#rpi4b><img src=https://img.shields.io/static/v1?label=&message=Standard&color=green></a></td><td align=left><a href=https://paste.armbian.com/idimigaboj><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>880</td><td align=right>5615</td><td align=right>beta</td></tr><tr><td align="left"><a id=rpi4b href=#rpi4b>Raspberry Pi 4</a></td><td align=center>6.7.0-rc5-edge-bcm2711</td><td align=center><a href=#rpi4b><img src=https://img.shields.io/static/v1?label=&message=Standard&color=green></a></td><td align=left><a href=https://paste.armbian.com/ebireqixam><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>880</td><td align=right>5228</td><td align=right>beta</td></tr><tr><td align="left"><a id=udoo href=#udoo>Udoo</a></td><td align=center>6.1.68-current-imx6</td><td align=center><a href=https://www.armbian.com/donate/><img src=https://img.shields.io/static/v1?label=&message=Community&color=white></a></td><td align=left><a href=https://paste.armbian.com/eduxojojum><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>332</td><td align=right>2374</td><td align=right>beta</td></tr><tr><td align="left"><a id=orangepi4-lts href=#orangepi4-lts>Orange Pi 4 LTS</a></td><td align=center>6.1.68-current-rockchip64</td><td align=center><a href=#orangepi4-lts><img src=https://img.shields.io/static/v1?label=&message=Standard&color=green></a></td><td align=left><a href=https://paste.armbian.com/omejazagiz><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>962</td><td align=right>5932</td><td align=right>beta</td></tr><tr><td align="left"><a id=orangepi4-lts href=#orangepi4-lts>Orange Pi 4 LTS</a></td><td align=center>6.6.7-edge-rockchip64</td><td align=center><a href=#orangepi4-lts><img src=https://img.shields.io/static/v1?label=&message=Standard&color=green></a></td><td align=left><a href=https://paste.armbian.com/xabeyetiho><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>880</td><td align=right>5796</td><td align=right>beta</td></tr><tr><td align="left"><a id=khadas-vim1s href=#khadas-vim1s>Khadas VIM1S</a></td><td align=center>5.4.180-legacy-meson-s4t7</td><td align=center><a href=#khadas-vim1s><img src=https://img.shields.io/static/v1?label=&message=Standard&color=green></a></td><td align=left><a href=https://paste.armbian.com/juqevodine><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>94</td><td align=right>3188</td><td align=right>beta</td></tr><tr><td align="left"><a id=nanopi-r6s href=#nanopi-r6s>NanoPi R6S</a></td><td align=center>5.10.160-legacy-rk35xx</td><td align=center><a href=#nanopi-r6s><img src=https://img.shields.io/static/v1?label=&message=Standard&color=green></a></td><td align=left><a href=https://paste.armbian.com/buyuxihomu><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>899</td><td align=right>15453</td><td align=right>beta</td></tr><tr><td align="left"><a id=nanopi-r6s href=#nanopi-r6s>NanoPi R6S</a></td><td align=center>5.10.160-legacy-rk35xx</td><td align=center><a href=#nanopi-r6s><img src=https://img.shields.io/static/v1?label=&message=Standard&color=green></a></td><td align=left><a href=https://paste.armbian.com/buyuxihomu><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>899</td><td align=right>15453</td><td align=right>beta</td></tr><tr><td align="left"><a id=nanopi-r1 href=#nanopi-r1>NanoPi R1</a></td><td align=center>n/a</td><td align=center><a href=https://www.armbian.com/donate/><img src=https://img.shields.io/static/v1?label=&message=Community&color=white></a></td><td align=left><img src=https://img.shields.io/static/v1?label=&message=n/a&color=white></td><td align=right>n/a</td><td align=right>n/a</td><td align=right></td></tr></table>
<!--END_SECTION:data-section-->

## Would you like to join spare hardware to this automated testings?

All you need to do is:

- deploy any latest Armbian image to hardware
- provide IP address
- [contact us](https://www.armbian.com/contact/)

Device has to be always on and easily accesible for you to re-image in case of failed upgrade.

## Development

- [Pull request](https://github.com/armbian/build/pulls)
- [Weekly developers meetings](https://forum.armbian.com/events/)
- [Forums for developers](https://forum.armbian.com/forum/4-advanced-users-development/)

## Download prebuilt images

- [quarterly released **supported** builds](https://www.armbian.com/download/?device_support=Standard%20support)
- [quarterly released **community maintained** builds](https://www.armbian.com/download/?device_support=Community%20maintained)
- [automatic released **rolling release** builds](https://github.com/armbian/os/releases/latest) (daily or when code changes)

## Support

- [Using Armbian](https://forum.armbian.com/forum/23-using-armbian/)

## Contact

- [Forums](https://forum.armbian.com) for Participate in Armbian
- IRC: `#armbian` on Libera.chat
- Discord: [https://discord.gg/armbian](https://discord.gg/armbian)
- Follow [@armbian](https://twitter.com/armbian) on X (formerly known as Twitter), [Fosstodon](https://fosstodon.org/@armbian) or [LinkedIn](https://www.linkedin.com/company/armbian).
- Bugs: [issues](https://github.com/armbian/build/issues) / [JIRA](https://armbian.atlassian.net/jira/dashboards/10000)
- Office hours: [Wednesday, 12 midday, 18 afternoon, CET](https://calendly.com/armbian/office-hours)
