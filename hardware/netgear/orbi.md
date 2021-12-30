### General

- To connect to your Orbi router directly go to [orbilogin.com](http://orbilogin.com) or [http://192.168.1.1/](http://192.168.1.1/)
    - Default username and password is admin and password, respectively.

### VPN

#### VPN Client

Netgear's firmware for the Orbi (as with the Nighthawk) supports only OpenVPN server for the purpose of reaching the Orbi LAN from outside.

**Options:**

- There is third party [firmware by voxel for the Orbi RBR50](http://www.voxel-firmware.com/Downloads/Voxel/html/orbi.html) that provides OpenVPN Client and also Wireguard.

- Buy a router with VPN Client abilities and connect it to your Orbi (with the Orbi in Access-Point mode).

- Orbis have a VPN Server service that you can enable and connect your devices to.

#### VPN Server

To enable the orbi VPN server service you will need to setup Dynamic DNS which will require a service provider.

**Dynamic DNS provider options:**

- [No-IP](https://www.noip.com/)
- [NETGEAR](https://www.netgear.com)
- [Dyn](https://www.dyn.com)

**!!IMPORTNANT!!**

If your ISP uses a CGNAT (e.g. (Aussie Broadband)[https://www.aussiebroadband.com.au/help-centre/internet/tech-support/cg-nat/]) then you will need to opt-out in order to do **port forwarding**.

