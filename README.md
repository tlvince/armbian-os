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


## What does this project do?

- Builds quarterly [stable](https://www.armbian.com/download/), daily [rolling](https://github.com/armbian/os/releases/latest) and weekly [community](https://github.com/armbian/community/releases/latest) OS images
- Keeps build framework [packages artifacts](https://github.com/orgs/armbian/packages) cache up to date to secure fast rebuild process
- Keeps stable [apt.armbian.com](https://apt.armbian.com) and nightly [beta.armbian.com](https://beta.armbian.com) packages repository up to date
- Keep synchronizing the selection of [3rd party](external) applications with Armbian repositories
- Reversion Firefox, Thunderbird and Chromium to higher (9) epoch version then its Snapd counterparts (1)
- Tests install of all packages added onto stable and testing Debian and Ubuntu releases
- Tests packages upgrade sucess on real hardware

## How to enable images?

Build lists are generated [automatic](https://github.com/armbian/os/blob/main/.github/workflows/recreate-matrix.yml#L59-L211C94) based on [support policy](https://docs.armbian.com/User-Guide_Board-Support-Rules/) and with help of [templates](userpatches/), .blacklist and .map files.

## When is this happening?

- Artifacts cache is updated every eight hours, starting at 0:00 AM UTC
- Repository update starts after artifacts cache update is done succesfully
- Smoke tests starts once per day at 5:30 AM UTC
- Nightly images are build once per day, at 2:00 AM UTC, or if [build config / template is changed](https://github.com/armbian/os/blob/main/userpatches/targets-release-nightly.yaml)
- Manually, when Armbian [release manager](https://github.com/orgs/armbian/teams/release-manager) executes a build action

## Latest smoke tests results:

- installs **kernels**, **device tree blob** and **headers**
- runs **network** (iperf) and **computing performance** tests (7z benchmark)
- store **armbianmonitor** logs

<!--START_SECTION:data-section-->
<table width="100%"><tr><td align="left"><a id=Board ID href=#Board ID><b>Board name</b></a></td><td align=center><b>Kernel version</b></td><td align=center><b>Support</b></td><td align=left><b>Logs</b></td><td align=right><b>Iperf</b></td><td align=right><b>7z -b</b></td><td align=right><b>Repo</b></td></tr><tr><td align="left"><a id=khadas-vim1 href=#khadas-vim1>Khadas VIM1</a></td><td align=center>6.6.22-current-meson64</td><td align=center><a href=https://docs.armbian.com/User-Guide_Board-Support-Rules/><img src=https://img.shields.io/static/v1?label=&message=Standard&color=green></a></td><td align=left><a href=https://paste.armbian.com/utuxogehem><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>90</td><td align=right>3717</td><td align=right>beta</td></tr><tr><td align="left"><a id=khadas-vim1 href=#khadas-vim1>Khadas VIM1</a></td><td align=center>6.7.10-edge-meson64</td><td align=center><a href=https://docs.armbian.com/User-Guide_Board-Support-Rules/><img src=https://img.shields.io/static/v1?label=&message=Standard&color=green></a></td><td align=left><a href=https://paste.armbian.com/umoguquluy><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>90</td><td align=right>3723</td><td align=right>beta</td></tr><tr><td align="left"><a id=orangepizeroplus href=#orangepizeroplus>Orange Pi Zero Plus</a></td><td align=center>6.6.22-current-sunxi64</td><td align=center><a href=https://docs.armbian.com/User-Guide_Board-Support-Rules/><img src=https://img.shields.io/static/v1?label=&message=Standard&color=green></a></td><td align=left><a href=https://paste.armbian.com/erocodalux><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>768</td><td align=right>2614</td><td align=right>beta</td></tr><tr><td align="left"><a id=orangepizeroplus href=#orangepizeroplus>Orange Pi Zero Plus</a></td><td align=center>6.7.10-edge-sunxi64</td><td align=center><a href=https://docs.armbian.com/User-Guide_Board-Support-Rules/><img src=https://img.shields.io/static/v1?label=&message=Standard&color=green></a></td><td align=left><a href=https://paste.armbian.com/ejeyohedox><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>841</td><td align=right>2600</td><td align=right>beta</td></tr><tr><td align="left"><a id=rockpi-e href=#rockpi-e>Rockpi E</a></td><td align=center>6.6.22-current-rockchip64</td><td align=center><a href=https://docs.armbian.com/User-Guide_Board-Support-Rules/><img src=https://img.shields.io/static/v1?label=&message=Standard&color=green></a></td><td align=left><a href=https://paste.armbian.com/iwekicayid><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>717</td><td align=right>3297</td><td align=right>beta</td></tr><tr><td align="left"><a id=rockpi-e href=#rockpi-e>Rockpi E</a></td><td align=center>6.7.10-edge-rockchip64</td><td align=center><a href=https://docs.armbian.com/User-Guide_Board-Support-Rules/><img src=https://img.shields.io/static/v1?label=&message=Standard&color=green></a></td><td align=left><a href=https://paste.armbian.com/pitetuhupi><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>101</td><td align=right>3372</td><td align=right>beta</td></tr><tr><td align="left"><a id=pineh64 href=#pineh64>Pine H64</a></td><td align=center>6.6.22-current-sunxi64</td><td align=center><a href=https://docs.armbian.com/User-Guide_Board-Support-Rules/><img src=https://img.shields.io/static/v1?label=&message=Community&color=white></a></td><td align=left><a href=https://paste.armbian.com/atatutatov><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>890</td><td align=right>4245</td><td align=right>beta</td></tr><tr><td align="left"><a id=pineh64 href=#pineh64>Pine H64</a></td><td align=center>6.7.10-edge-sunxi64</td><td align=center><a href=https://docs.armbian.com/User-Guide_Board-Support-Rules/><img src=https://img.shields.io/static/v1?label=&message=Community&color=white></a></td><td align=left><a href=https://paste.armbian.com/igalotewut><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>820</td><td align=right>4291</td><td align=right>beta</td></tr><tr><td align="left"><a id=lime-a64 href=#lime-a64>A64 OLinuXino</a></td><td align=center>n/a</td><td align=center><a href=https://docs.armbian.com/User-Guide_Board-Support-Rules/><img src=https://img.shields.io/static/v1?label=&message=Community&color=white></a></td><td align=left><img src=https://img.shields.io/static/v1?label=&message=n/a&color=white></td><td align=right>n/a</td><td align=right>n/a</td><td align=right></td></tr><tr><td align="left"><a id=lime-a64 href=#lime-a64>A64 OLinuXino</a></td><td align=center>n/a</td><td align=center><a href=https://docs.armbian.com/User-Guide_Board-Support-Rules/><img src=https://img.shields.io/static/v1?label=&message=Community&color=white></a></td><td align=left><img src=https://img.shields.io/static/v1?label=&message=n/a&color=white></td><td align=right>n/a</td><td align=right>n/a</td><td align=right></td></tr><tr><td align="left"><a id=lime-a64 href=#lime-a64>A64 OLinuXino</a></td><td align=center>n/a</td><td align=center><a href=https://docs.armbian.com/User-Guide_Board-Support-Rules/><img src=https://img.shields.io/static/v1?label=&message=Community&color=white></a></td><td align=left><img src=https://img.shields.io/static/v1?label=&message=n/a&color=white></td><td align=right>n/a</td><td align=right>n/a</td><td align=right></td></tr><tr><td align="left"><a id=bananapim2pro href=#bananapim2pro>Banana Pi M2Pro</a></td><td align=center>6.6.22-current-meson64</td><td align=center><a href=https://docs.armbian.com/User-Guide_Board-Support-Rules/><img src=https://img.shields.io/static/v1?label=&message=Standard&color=green></a></td><td align=left><a href=https://paste.armbian.com/enaguporaz><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>870</td><td align=right>5308</td><td align=right>beta</td></tr><tr><td align="left"><a id=bananapim2pro href=#bananapim2pro>Banana Pi M2Pro</a></td><td align=center>6.7.10-edge-meson64</td><td align=center><a href=https://docs.armbian.com/User-Guide_Board-Support-Rules/><img src=https://img.shields.io/static/v1?label=&message=Standard&color=green></a></td><td align=left><a href=https://paste.armbian.com/sukipagele><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>860</td><td align=right>5305</td><td align=right>beta</td></tr><tr><td align="left"><a id=lepotato href=#lepotato>Le potato</a></td><td align=center>6.6.22-current-meson64</td><td align=center><a href=https://docs.armbian.com/User-Guide_Board-Support-Rules/><img src=https://img.shields.io/static/v1?label=&message=Standard&color=green></a></td><td align=left><a href=https://paste.armbian.com/ozegibefix><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>90</td><td align=right>3673</td><td align=right>beta</td></tr><tr><td align="left"><a id=lepotato href=#lepotato>Le potato</a></td><td align=center>6.7.10-edge-meson64</td><td align=center><a href=https://docs.armbian.com/User-Guide_Board-Support-Rules/><img src=https://img.shields.io/static/v1?label=&message=Standard&color=green></a></td><td align=left><a href=https://paste.armbian.com/soyubotiki><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>91</td><td align=right>3732</td><td align=right>beta</td></tr><tr><td align="left"><a id=orangepi5 href=#orangepi5>Orange Pi 5</a></td><td align=center>5.10.160-legacy-rk35xx</td><td align=center><a href=https://docs.armbian.com/User-Guide_Board-Support-Rules/><img src=https://img.shields.io/static/v1?label=&message=Standard&color=green></a></td><td align=left><a href=https://paste.armbian.com/niququtobo><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>910</td><td align=right>15765</td><td align=right>beta</td></tr><tr><td align="left"><a id=tinkerboard href=#tinkerboard>Tinker Board</a></td><td align=center>n/a</td><td align=center><a href=https://docs.armbian.com/User-Guide_Board-Support-Rules/><img src=https://img.shields.io/static/v1?label=&message=Standard&color=green></a></td><td align=left><img src=https://img.shields.io/static/v1?label=&message=n/a&color=white></td><td align=right>n/a</td><td align=right>n/a</td><td align=right></td></tr><tr><td align="left"><a id=nanopineo2black href=#nanopineo2black>NanoPi Neo 2 Black</a></td><td align=center>n/a</td><td align=center><a href=https://docs.armbian.com/User-Guide_Board-Support-Rules/><img src=https://img.shields.io/static/v1?label=&message=Community&color=white></a></td><td align=left><img src=https://img.shields.io/static/v1?label=&message=n/a&color=white></td><td align=right>n/a</td><td align=right>n/a</td><td align=right></td></tr><tr><td align="left"><a id=nanopineo2black href=#nanopineo2black>NanoPi Neo 2 Black</a></td><td align=center>n/a</td><td align=center><a href=https://docs.armbian.com/User-Guide_Board-Support-Rules/><img src=https://img.shields.io/static/v1?label=&message=Community&color=white></a></td><td align=left><img src=https://img.shields.io/static/v1?label=&message=n/a&color=white></td><td align=right>n/a</td><td align=right>n/a</td><td align=right></td></tr><tr><td align="left"><a id=nanopineo2black href=#nanopineo2black>NanoPi Neo 2 Black</a></td><td align=center>n/a</td><td align=center><a href=https://docs.armbian.com/User-Guide_Board-Support-Rules/><img src=https://img.shields.io/static/v1?label=&message=Community&color=white></a></td><td align=left><img src=https://img.shields.io/static/v1?label=&message=n/a&color=white></td><td align=right>n/a</td><td align=right>n/a</td><td align=right></td></tr><tr><td align="left"><a id=khadas-vim2 href=#khadas-vim2>Khadas VIM2</a></td><td align=center>6.6.22-current-meson64</td><td align=center><a href=https://docs.armbian.com/User-Guide_Board-Support-Rules/><img src=https://img.shields.io/static/v1?label=&message=Standard&color=green></a></td><td align=left><a href=https://paste.armbian.com/suhajasibo><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>710</td><td align=right>6139</td><td align=right>beta</td></tr><tr><td align="left"><a id=khadas-vim2 href=#khadas-vim2>Khadas VIM2</a></td><td align=center>6.7.10-edge-meson64</td><td align=center><a href=https://docs.armbian.com/User-Guide_Board-Support-Rules/><img src=https://img.shields.io/static/v1?label=&message=Standard&color=green></a></td><td align=left><a href=https://paste.armbian.com/ocegeceyid><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>876</td><td align=right>6122</td><td align=right>beta</td></tr><tr><td align="left"><a id=orangepizero2 href=#orangepizero2>Orange Pi Zero2</a></td><td align=center>6.6.22-current-sunxi64</td><td align=center><a href=https://docs.armbian.com/User-Guide_Board-Support-Rules/><img src=https://img.shields.io/static/v1?label=&message=Standard&color=green></a></td><td align=left><a href=https://paste.armbian.com/><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>680</td><td align=right>2912</td><td align=right>beta</td></tr><tr><td align="left"><a id=orangepizero2 href=#orangepizero2>Orange Pi Zero2</a></td><td align=center>6.7.10-edge-sunxi64</td><td align=center><a href=https://docs.armbian.com/User-Guide_Board-Support-Rules/><img src=https://img.shields.io/static/v1?label=&message=Standard&color=green></a></td><td align=left><a href=https://paste.armbian.com/><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>827</td><td align=right>3164</td><td align=right>beta</td></tr><tr><td align="left"><a id=khadas-vim3 href=#khadas-vim3>Khadas VIM3</a></td><td align=center>6.6.22-current-meson64</td><td align=center><a href=https://docs.armbian.com/User-Guide_Board-Support-Rules/><img src=https://img.shields.io/static/v1?label=&message=Standard&color=green></a></td><td align=left><a href=https://paste.armbian.com/ehofubulig><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>960</td><td align=right>9624</td><td align=right>beta</td></tr><tr><td align="left"><a id=khadas-vim3 href=#khadas-vim3>Khadas VIM3</a></td><td align=center>6.7.10-edge-meson64</td><td align=center><a href=https://docs.armbian.com/User-Guide_Board-Support-Rules/><img src=https://img.shields.io/static/v1?label=&message=Standard&color=green></a></td><td align=left><a href=https://paste.armbian.com/zenuyojora><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>860</td><td align=right>9555</td><td align=right>beta</td></tr><tr><td align="left"><a id=khadas-vim1s href=#khadas-vim1s>Khadas VIM1S</a></td><td align=center>5.15.119-legacy-meson-s4t7</td><td align=center><a href=https://docs.armbian.com/User-Guide_Board-Support-Rules/><img src=https://img.shields.io/static/v1?label=&message=Standard&color=green></a></td><td align=left><a href=https://paste.armbian.com/sitivuwuwa><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>91</td><td align=right>3486</td><td align=right>beta</td></tr><tr><td align="left"><a id=tanix-tx6 href=#tanix-tx6>Tanix TX6</a></td><td align=center>6.6.22-current-sunxi64</td><td align=center><a href=https://docs.armbian.com/User-Guide_Board-Support-Rules/><img src=https://img.shields.io/static/v1?label=&message=Community&color=white></a></td><td align=left><a href=https://paste.armbian.com/reruzisaya><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>90</td><td align=right>4231</td><td align=right>beta</td></tr><tr><td align="left"><a id=tanix-tx6 href=#tanix-tx6>Tanix TX6</a></td><td align=center>6.7.10-edge-sunxi64</td><td align=center><a href=https://docs.armbian.com/User-Guide_Board-Support-Rules/><img src=https://img.shields.io/static/v1?label=&message=Community&color=white></a></td><td align=left><a href=https://paste.armbian.com/uwimudakuy><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>91</td><td align=right>4287</td><td align=right>beta</td></tr><tr><td align="left"><a id=khadas-vim4 href=#khadas-vim4>Khadas VIM4</a></td><td align=center>n/a</td><td align=center><a href=https://docs.armbian.com/User-Guide_Board-Support-Rules/><img src=https://img.shields.io/static/v1?label=&message=Standard&color=green></a></td><td align=left><img src=https://img.shields.io/static/v1?label=&message=n/a&color=white></td><td align=right>n/a</td><td align=right>n/a</td><td align=right></td></tr><tr><td align="left"><a id=nanopim4 href=#nanopim4>NanoPi M4</a></td><td align=center>6.6.22-current-rockchip64</td><td align=center><a href=https://docs.armbian.com/User-Guide_Board-Support-Rules/><img src=https://img.shields.io/static/v1?label=&message=Community&color=white></a></td><td align=left><a href=https://paste.armbian.com/fenunoheni><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>840</td><td align=right>6611</td><td align=right>beta</td></tr><tr><td align="left"><a id=nanopim4 href=#nanopim4>NanoPi M4</a></td><td align=center>6.7.10-edge-rockchip64</td><td align=center><a href=https://docs.armbian.com/User-Guide_Board-Support-Rules/><img src=https://img.shields.io/static/v1?label=&message=Community&color=white></a></td><td align=left><a href=https://paste.armbian.com/balahevute><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>710</td><td align=right>6602</td><td align=right>beta</td></tr><tr><td align="left"><a id=bananapim5 href=#bananapim5>Banana Pi M5</a></td><td align=center>6.6.22-current-meson64</td><td align=center><a href=https://docs.armbian.com/User-Guide_Board-Support-Rules/><img src=https://img.shields.io/static/v1?label=&message=Standard&color=green></a></td><td align=left><a href=https://paste.armbian.com/><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>780</td><td align=right>5524</td><td align=right>beta</td></tr><tr><td align="left"><a id=bananapim5 href=#bananapim5>Banana Pi M5</a></td><td align=center>6.7.10-edge-meson64</td><td align=center><a href=https://docs.armbian.com/User-Guide_Board-Support-Rules/><img src=https://img.shields.io/static/v1?label=&message=Standard&color=green></a></td><td align=left><a href=https://paste.armbian.com/><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>760</td><td align=right>5547</td><td align=right>beta</td></tr><tr><td align="left"><a id=udoo href=#udoo>Udoo</a></td><td align=center>6.6.22-current-imx6</td><td align=center><a href=https://docs.armbian.com/User-Guide_Board-Support-Rules/><img src=https://img.shields.io/static/v1?label=&message=Community&color=white></a></td><td align=left><a href=https://paste.armbian.com/ewiwararab><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>341</td><td align=right>2372</td><td align=right>beta</td></tr><tr><td align="left"><a id=orangepizero href=#orangepizero>Orange Pi Zero</a></td><td align=center>6.6.22-current-sunxi</td><td align=center><a href=https://docs.armbian.com/User-Guide_Board-Support-Rules/><img src=https://img.shields.io/static/v1?label=&message=Standard&color=green></a></td><td align=left><a href=https://paste.armbian.com/pusaluwimu><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>89</td><td align=right>2639</td><td align=right>beta</td></tr><tr><td align="left"><a id=odroidc4 href=#odroidc4>Odroid C4</a></td><td align=center>6.6.22-current-meson64</td><td align=center><a href=https://docs.armbian.com/User-Guide_Board-Support-Rules/><img src=https://img.shields.io/static/v1?label=&message=Community&color=white></a></td><td align=left><a href=https://paste.armbian.com/jonecedile><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>790</td><td align=right>5640</td><td align=right>beta</td></tr><tr><td align="left"><a id=odroidc4 href=#odroidc4>Odroid C4</a></td><td align=center>6.7.10-edge-meson64</td><td align=center><a href=https://docs.armbian.com/User-Guide_Board-Support-Rules/><img src=https://img.shields.io/static/v1?label=&message=Community&color=white></a></td><td align=left><a href=https://paste.armbian.com/mugovoziyi><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>730</td><td align=right>5608</td><td align=right>beta</td></tr><tr><td align="left"><a id=odroidc2 href=#odroidc2>Odroid C2</a></td><td align=center>n/a</td><td align=center><a href=https://docs.armbian.com/User-Guide_Board-Support-Rules/><img src=https://img.shields.io/static/v1?label=&message=Standard&color=green></a></td><td align=left><img src=https://img.shields.io/static/v1?label=&message=n/a&color=white></td><td align=right>n/a</td><td align=right>n/a</td><td align=right></td></tr><tr><td align="left"><a id=odroidc2 href=#odroidc2>Odroid C2</a></td><td align=center>n/a</td><td align=center><a href=https://docs.armbian.com/User-Guide_Board-Support-Rules/><img src=https://img.shields.io/static/v1?label=&message=Standard&color=green></a></td><td align=left><img src=https://img.shields.io/static/v1?label=&message=n/a&color=white></td><td align=right>n/a</td><td align=right>n/a</td><td align=right></td></tr><tr><td align="left"><a id=rpi4b href=#rpi4b>Raspberry Pi 4</a></td><td align=center>6.6.22-current-bcm2711</td><td align=center><a href=https://docs.armbian.com/User-Guide_Board-Support-Rules/><img src=https://img.shields.io/static/v1?label=&message=Standard&color=green></a></td><td align=left><a href=https://paste.armbian.com/fejulireqo><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>90</td><td align=right>3015</td><td align=right>beta</td></tr><tr><td align="left"><a id=rpi4b href=#rpi4b>Raspberry Pi 4</a></td><td align=center>6.7.10-edge-bcm2711</td><td align=center><a href=https://docs.armbian.com/User-Guide_Board-Support-Rules/><img src=https://img.shields.io/static/v1?label=&message=Standard&color=green></a></td><td align=left><a href=https://paste.armbian.com/fozugubire><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>90</td><td align=right>3036</td><td align=right>beta</td></tr><tr><td align="left"><a id=nanopineo3 href=#nanopineo3>NanoPi Neo 3</a></td><td align=center>n/a</td><td align=center><a href=https://docs.armbian.com/User-Guide_Board-Support-Rules/><img src=https://img.shields.io/static/v1?label=&message=Community&color=white></a></td><td align=left><img src=https://img.shields.io/static/v1?label=&message=n/a&color=white></td><td align=right>n/a</td><td align=right>n/a</td><td align=right></td></tr><tr><td align="left"><a id=bananapim2ultra href=#bananapim2ultra>Banana Pi M2 Ultra</a></td><td align=center>6.6.22-current-sunxi</td><td align=center><a href=https://docs.armbian.com/User-Guide_Board-Support-Rules/><img src=https://img.shields.io/static/v1?label=&message=Community&color=white></a></td><td align=left><a href=https://paste.armbian.com/ucenecozef><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>734</td><td align=right>2688</td><td align=right>beta</td></tr><tr><td align="left"><a id=tinkerboard-2 href=#tinkerboard-2>Tinker Board 2</a></td><td align=center>n/a</td><td align=center><a href=https://docs.armbian.com/User-Guide_Board-Support-Rules/><img src=https://img.shields.io/static/v1?label=&message=Community&color=white></a></td><td align=left><img src=https://img.shields.io/static/v1?label=&message=n/a&color=white></td><td align=right>n/a</td><td align=right>n/a</td><td align=right></td></tr><tr><td align="left"><a id=orangepi5-plus href=#orangepi5-plus>Orange Pi 5 Plus</a></td><td align=center>n/a</td><td align=center><a href=https://docs.armbian.com/User-Guide_Board-Support-Rules/><img src=https://img.shields.io/static/v1?label=&message=Standard&color=green></a></td><td align=left><img src=https://img.shields.io/static/v1?label=&message=n/a&color=white></td><td align=right>n/a</td><td align=right>n/a</td><td align=right>beta</td></tr><tr><td align="left"><a id=orangepi-r1plus-lts href=#orangepi-r1plus-lts>Orange Pi R1 Plus LTS</a></td><td align=center>n/a</td><td align=center><a href=https://docs.armbian.com/User-Guide_Board-Support-Rules/><img src=https://img.shields.io/static/v1?label=&message=Community&color=white></a></td><td align=left><img src=https://img.shields.io/static/v1?label=&message=n/a&color=white></td><td align=right>n/a</td><td align=right>n/a</td><td align=right></td></tr><tr><td align="left"><a id=uefi-x86 href=#uefi-x86>UEFI x86</a></td><td align=center>6.1.82-legacy-x86</td><td align=center><a href=https://docs.armbian.com/User-Guide_Board-Support-Rules/><img src=https://img.shields.io/static/v1?label=&message=Standard&color=green></a></td><td align=left><a href=https://paste.armbian.com/jadozibinu><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>860</td><td align=right>4761</td><td align=right>beta</td></tr><tr><td align="left"><a id=uefi-x86 href=#uefi-x86>UEFI x86</a></td><td align=center>6.6.22-current-x86</td><td align=center><a href=https://docs.armbian.com/User-Guide_Board-Support-Rules/><img src=https://img.shields.io/static/v1?label=&message=Standard&color=green></a></td><td align=left><a href=https://paste.armbian.com/gegamubafa><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>834</td><td align=right>4831</td><td align=right>beta</td></tr><tr><td align="left"><a id=uefi-x86 href=#uefi-x86>UEFI x86</a></td><td align=center>6.8.1-edge-x86</td><td align=center><a href=https://docs.armbian.com/User-Guide_Board-Support-Rules/><img src=https://img.shields.io/static/v1?label=&message=Standard&color=green></a></td><td align=left><a href=https://paste.armbian.com/gibenuloca><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>808</td><td align=right>4819</td><td align=right>beta</td></tr><tr><td align="left"><a id=odroidn2 href=#odroidn2>Odroid N2</a></td><td align=center>n/a</td><td align=center><a href=https://docs.armbian.com/User-Guide_Board-Support-Rules/><img src=https://img.shields.io/static/v1?label=&message=Standard&color=green></a></td><td align=left><img src=https://img.shields.io/static/v1?label=&message=n/a&color=white></td><td align=right>n/a</td><td align=right>n/a</td><td align=right></td></tr><tr><td align="left"><a id=odroidn2 href=#odroidn2>Odroid N2</a></td><td align=center>n/a</td><td align=center><a href=https://docs.armbian.com/User-Guide_Board-Support-Rules/><img src=https://img.shields.io/static/v1?label=&message=Standard&color=green></a></td><td align=left><img src=https://img.shields.io/static/v1?label=&message=n/a&color=white></td><td align=right>n/a</td><td align=right>n/a</td><td align=right></td></tr><tr><td align="left"><a id=zeropi href=#zeropi>ZeroPi</a></td><td align=center>n/a</td><td align=center><a href=https://docs.armbian.com/User-Guide_Board-Support-Rules/><img src=https://img.shields.io/static/v1?label=&message=Community&color=white></a></td><td align=left><img src=https://img.shields.io/static/v1?label=&message=n/a&color=white></td><td align=right>n/a</td><td align=right>n/a</td><td align=right>beta</td></tr><tr><td align="left"><a id=bigtreetech-cb1 href=#bigtreetech-cb1>BigTreeTech CB1</a></td><td align=center>6.1.79-legacy-sun50iw9-btt</td><td align=center><a href=https://docs.armbian.com/User-Guide_Board-Support-Rules/><img src=https://img.shields.io/static/v1?label=&message=Standard&color=green></a></td><td align=left><a href=https://paste.armbian.com/yoqayukole><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>89</td><td align=right>2683</td><td align=right>beta</td></tr><tr><td align="left"><a id=jetson-nano href=#jetson-nano>Jetson Nano</a></td><td align=center>6.6.22-current-arm64</td><td align=center><a href=https://docs.armbian.com/User-Guide_Board-Support-Rules/><img src=https://img.shields.io/static/v1?label=&message=Community&color=white></a></td><td align=left><a href=https://paste.armbian.com/opayuzimig><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>636</td><td align=right>3968</td><td align=right>beta</td></tr><tr><td align="left"><a id=jetson-nano href=#jetson-nano>Jetson Nano</a></td><td align=center>6.8.1-edge-arm64</td><td align=center><a href=https://docs.armbian.com/User-Guide_Board-Support-Rules/><img src=https://img.shields.io/static/v1?label=&message=Community&color=white></a></td><td align=left><a href=https://paste.armbian.com/iqugiqipil><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>884</td><td align=right>4030</td><td align=right>beta</td></tr><tr><td align="left"><a id=bananapicm4io href=#bananapicm4io>Banana Pi CM4IO</a></td><td align=center>6.4.13-edge-meson64</td><td align=center><a href=https://docs.armbian.com/User-Guide_Board-Support-Rules/><img src=https://img.shields.io/static/v1?label=&message=Standard&color=green></a></td><td align=left><a href=https://paste.armbian.com/papaboxuze><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>810</td><td align=right>9510</td><td align=right>beta</td></tr><tr><td align="left"><a id=bananapicm4io href=#bananapicm4io>Banana Pi CM4IO</a></td><td align=center>6.4.13-edge-meson64</td><td align=center><a href=https://docs.armbian.com/User-Guide_Board-Support-Rules/><img src=https://img.shields.io/static/v1?label=&message=Standard&color=green></a></td><td align=left><a href=https://paste.armbian.com/uzebenetoz><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>800</td><td align=right>9363</td><td align=right>beta</td></tr><tr><td align="left"><a id=odroidm1 href=#odroidm1>Odroid M1</a></td><td align=center>6.6.4-edge-rk3568-odroid</td><td align=center><a href=https://docs.armbian.com/User-Guide_Board-Support-Rules/><img src=https://img.shields.io/static/v1?label=&message=Standard&color=green></a></td><td align=left><a href=https://paste.armbian.com/hidumazuho><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>589</td><td align=right>5307</td><td align=right>beta</td></tr><tr><td align="left"><a id=odroidm1 href=#odroidm1>Odroid M1</a></td><td align=center>6.6.4-edge-rk3568-odroid</td><td align=center><a href=https://docs.armbian.com/User-Guide_Board-Support-Rules/><img src=https://img.shields.io/static/v1?label=&message=Standard&color=green></a></td><td align=left><a href=https://paste.armbian.com/wutewamile><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>472</td><td align=right>5241</td><td align=right>beta</td></tr><tr><td align="left"><a id=nanopi-r4s href=#nanopi-r4s>NanoPi R4S</a></td><td align=center>6.6.22-current-rockchip64</td><td align=center><a href=https://docs.armbian.com/User-Guide_Board-Support-Rules/><img src=https://img.shields.io/static/v1?label=&message=Standard&color=green></a></td><td align=left><a href=https://paste.armbian.com/itowopumer><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>974</td><td align=right>6539</td><td align=right>beta</td></tr><tr><td align="left"><a id=nanopi-r4s href=#nanopi-r4s>NanoPi R4S</a></td><td align=center>6.7.10-edge-rockchip64</td><td align=center><a href=https://docs.armbian.com/User-Guide_Board-Support-Rules/><img src=https://img.shields.io/static/v1?label=&message=Standard&color=green></a></td><td align=left><a href=https://paste.armbian.com/akaxabobar><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>910</td><td align=right>6593</td><td align=right>beta</td></tr><tr><td align="left"><a id=rpi4b href=#rpi4b>Raspberry Pi 4</a></td><td align=center>6.6.22-current-bcm2711</td><td align=center><a href=https://docs.armbian.com/User-Guide_Board-Support-Rules/><img src=https://img.shields.io/static/v1?label=&message=Standard&color=green></a></td><td align=left><a href=https://paste.armbian.com/vifugebete><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>690</td><td align=right>2810</td><td align=right>beta</td></tr><tr><td align="left"><a id=rpi4b href=#rpi4b>Raspberry Pi 4</a></td><td align=center>6.7.10-edge-bcm2711</td><td align=center><a href=https://docs.armbian.com/User-Guide_Board-Support-Rules/><img src=https://img.shields.io/static/v1?label=&message=Standard&color=green></a></td><td align=left><a href=https://paste.armbian.com/vunegorixe><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>730</td><td align=right>4415</td><td align=right>beta</td></tr><tr><td align="left"><a id=nanopi-r6s href=#nanopi-r6s>NanoPi R6S</a></td><td align=center>5.10.160-legacy-rk35xx</td><td align=center><a href=https://docs.armbian.com/User-Guide_Board-Support-Rules/><img src=https://img.shields.io/static/v1?label=&message=Community&color=white></a></td><td align=left><a href=https://paste.armbian.com/usejevubuj><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>980</td><td align=right>15655</td><td align=right>beta</td></tr><tr><td align="left"><a id=nanopi-r6s href=#nanopi-r6s>NanoPi R6S</a></td><td align=center>5.10.160-legacy-rk35xx</td><td align=center><a href=https://docs.armbian.com/User-Guide_Board-Support-Rules/><img src=https://img.shields.io/static/v1?label=&message=Community&color=white></a></td><td align=left><a href=https://paste.armbian.com/usejevubuj><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>980</td><td align=right>15655</td><td align=right>beta</td></tr><tr><td align="left"><a id=orangepilite2 href=#orangepilite2>Orange Pi Lite 2</a></td><td align=center>6.1.82-legacy-sunxi64</td><td align=center><a href=https://docs.armbian.com/User-Guide_Board-Support-Rules/><img src=https://img.shields.io/static/v1?label=&message=Community&color=white></a></td><td align=left><a href=https://paste.armbian.com/jaluferifa><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>69</td><td align=right>3938</td><td align=right>beta</td></tr><tr><td align="left"><a id=orangepilite2 href=#orangepilite2>Orange Pi Lite 2</a></td><td align=center>6.6.22-current-sunxi64</td><td align=center><a href=https://docs.armbian.com/User-Guide_Board-Support-Rules/><img src=https://img.shields.io/static/v1?label=&message=Community&color=white></a></td><td align=left><a href=https://paste.armbian.com/towajimeru><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>51</td><td align=right>3797</td><td align=right>beta</td></tr><tr><td align="left"><a id=orangepilite2 href=#orangepilite2>Orange Pi Lite 2</a></td><td align=center>6.7.10-edge-sunxi64</td><td align=center><a href=https://docs.armbian.com/User-Guide_Board-Support-Rules/><img src=https://img.shields.io/static/v1?label=&message=Community&color=white></a></td><td align=left><a href=https://paste.armbian.com/xipufejewi><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>12</td><td align=right>4011</td><td align=right>beta</td></tr><tr><td align="left"><a id=orangepizeroplus2-h3 href=#orangepizeroplus2-h3>Orange Pi Zero Plus 2</a></td><td align=center>6.6.22-current-sunxi</td><td align=center><a href=https://docs.armbian.com/User-Guide_Board-Support-Rules/><img src=https://img.shields.io/static/v1?label=&message=Community&color=white></a></td><td align=left><a href=https://paste.armbian.com/yayutiwuwi><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>9</td><td align=right>2596</td><td align=right>beta</td></tr><tr><td align="left"><a id=orangepizeroplus2-h3 href=#orangepizeroplus2-h3>Orange Pi Zero Plus 2</a></td><td align=center>6.7.10-edge-sunxi</td><td align=center><a href=https://docs.armbian.com/User-Guide_Board-Support-Rules/><img src=https://img.shields.io/static/v1?label=&message=Community&color=white></a></td><td align=left><a href=https://paste.armbian.com/hofowezana><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>7</td><td align=right>2645</td><td align=right>beta</td></tr></table>
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

- [quarterly released **standard support** builds](https://www.armbian.com/download/?device_support=Standard%20support)
- [automatic released **rolling release** builds](https://github.com/armbian/os/releases/latest) (daily or when code changes)
- [weekly released **community maintained** builds](https://github.com/armbian/community/releases/latest)

## Support

- [Using Armbian](https://forum.armbian.com/forum/23-using-armbian/)

## Contact

- [Forums](https://forum.armbian.com) for Participate in Armbian
- IRC: `#armbian` on Libera.chat
- Discord: [https://discord.gg/armbian](https://discord.gg/armbian)
- Follow [@armbian](https://twitter.com/armbian) on X (formerly known as Twitter), [Fosstodon](https://fosstodon.org/@armbian) or [LinkedIn](https://www.linkedin.com/company/armbian).
- Bugs: [issues](https://github.com/armbian/build/issues) / [JIRA](https://armbian.atlassian.net/jira/dashboards/10000)
- Office hours: [Wednesday, 12 midday, 18 afternoon, CET](https://calendly.com/armbian/office-hours)
