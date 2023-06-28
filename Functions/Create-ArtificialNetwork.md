![Logo](https://github.com/I-Am-Jakoby/hak5-submissions/blob/main/Assets/logo-170-px.png?raw=true)

<!-- TABLE OF CONTENTS -->
<details>
  <summary>Table of Contents</summary>
  <ol>
    <li><a href="#Description">Description</a></li>
    <li><a href="#The-Function">The Function</a></li>
    <li><a href="#Acknowledgments">Acknowledgments</a></li>
  </ol>
</details>

# Create-ArtificialNetwork

## Description

This function creates a virtual network that can be connected to

## The Function

### [Create-ArtificialNetwork]

Using the netsh command, an artificial network is created
The network name and password are stored as $SSID and $Password as the variables

```
function Create-ArtificialNetwork {
    [CmdletBinding()]
    param (
        [Parameter(Mandatory = $true, Position = 0)]
        [string]$SSID,

        [Parameter(Mandatory = $true, Position = 1)]
        [string]$Password
    )

    # Create a virtual Wi-Fi network using netsh
    $netshCommand = "netsh wlan set hostednetwork mode=allow ssid='$SSID' key='$Password'"
    $netshCommand += "; netsh wlan start hostednetwork"

    # Execute the netsh commands
    Invoke-Expression -Command $netshCommand
}
```

This would be used like this:
``
Create-ArtificalNetwork -SSID (Network Name) -Password (Network Password)
``

If you don't set a password, it will still show up as a network however you can't connect to it.
A password is also required, it can't be an open network.

<p align="right">(<a href="#top">back to top</a>)</p>

<!-- ACKNOWLEDGMENTS -->
## Acknowledgments

* [Hak5](https://hak5.org/)
* [UberGuidoZ](https://github.com/UberGuidoZ)

***

[HOME-PAGE](https://github.com/I-Am-Jakoby/PowerShell-for-Hackers)

<p align="right">(<a href="#top">back to top</a>)</p>