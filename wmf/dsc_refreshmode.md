### Additional Value for RefreshMode Property

This release introduces a new RefreshMode value, **Disabled**. When this mode is set, LCM does not do document management. This mode can be used when a third party configuration management tool is used instead of DSC while still making use of DSC Resources with the Invoke-DscResource cmdlet or if you just need to stop DSC processing for any reason.

Configuration LCMSettings

{

    Node localhost

    {

        LocalConfigurationManager

        {

           RefreshMode = 'Disabled'

        }

    }

}

LCMSettings -OutputPath .\\LCMSettings

Set-DscLocalConfigurationManager -Path .\\LCMSettings -Verbose -ComputerName localhost

