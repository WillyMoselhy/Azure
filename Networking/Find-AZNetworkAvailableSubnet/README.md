# Find-AZVirtualNetworkAvailableSubnet

## Examples
``` PowerShell
$RGName = "AutoSubnetRG"
$vNetName = "AutoSubnetVNet"
$SubnetName = "MyNewSubnet"

$NewSubnet = Find-AZVirtualNetworkAvailableSubnet -ResourceGroupName $RGName -vNetName $vNetName -AddressSpace 10.0.0.0/16 -NewSubnetMaskBits 24 | Select -First 1

Get-AzVirtualNetwork -ResourceGroupName $RGName -Name $vNetName | Add-AzVirtualNetworkSubnetConfig -Name $SubnetName -AddressPrefix $NewSubnet.AddressPrefix | Set-AzVirtualNetwork
```