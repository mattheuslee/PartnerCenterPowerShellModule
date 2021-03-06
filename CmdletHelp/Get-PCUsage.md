# Get-PCUsage

Retrieve a collection of usage records for the specified date range. Usage records are only available for the last 90 days.

## SYNTAX

```powershell
Get-PCUsage -SubscriptionId <String> -StartTime <String> -EndTime <String> [-Granularity <String>] [-ShowDetail <Boolean>] [-ResultSize <Int32>] [-TenantId <String>] [-SaToken <String>] [<CommonParameters>]
```

## DESCRIPTION

The Get-PCUsage cmdlet returns the usage records specified by the start and end times.

## PARAMETERS

### -SubscriptionId &lt;String&gt;

Specifies a subscription if for which to return usage information.

```yaml
Required?                    true
Position?                    named
Default value
Accept pipeline input?       false
Accept wildcard characters?  false
```

### -StartTime &lt;String&gt;

Specifies the start time for which to retrieve usage information. Usage is only available for the last 90 days, therefore this value cannot be more than 90 days from the current date.

```yaml
Required?                    true
Position?                    named
Default value
Accept pipeline input?       false
Accept wildcard characters?  false
```

### -EndTime &lt;String&gt;

Specifies the end time for which to retrieve usage information.

```yaml
Required?                    true
Position?                    named
Default value
Accept pipeline input?       false
Accept wildcard characters?  false
```

### -Granularity &lt;String&gt;

Specifies the granularity of the data to return. Valid values are: daily or hourly. The default value is daily.

```yaml
Required?                    false
Position?                    named
Default value                daily
Accept pipeline input?       false
Accept wildcard characters?  false
```

### -ShowDetail &lt;Boolean&gt;

Default this is set to $true. If set to $true, the utilization records will be split by the resource instance levels. If set to false, the utilization records will be aggregated on the resource level.

```yaml
Required?                    false
Position?                    named
Default value                True
Accept pipeline input?       false
Accept wildcard characters?  false
```

### -ResultSize &lt;Int32&gt;

Specifies the maximum number of results to return. The default value is 1000.

```yaml
Required?                    false
Position?                    named
Default value                1000
Accept pipeline input?       false
Accept wildcard characters?  false
```

### -TenantId &lt;String&gt;

Specifies the tenant used for scoping this cmdlet.

```yaml
Required?                    false
Position?                    named
Default value                $GlobalCustomerId
Accept pipeline input?       false
Accept wildcard characters?  false
```

### -SaToken &lt;String&gt;

Specifies a authentication token you have created with your Partner Center credentials.

```yaml
Required?                    false
Position?                    named
Default value                $GlobalToken
Accept pipeline input?       false
Accept wildcard characters?  false
```

## INPUTS

## OUTPUTS

## NOTES

## EXAMPLES

### EXAMPLE 1

Return up to 2000 hourly usage records for the specified date range.

```powershell
PS C:\>Get-PCUsage -TenantId 2a14b164-f983-4048-92e1-4f9591b87445 -SubscriptionId b027a4b3-5487-413b-aa48-ec8733c874d6 -StartTime '06-12-2018 00:00:00' -EndTime '06-30-2018 23:59:59' -Granularity hourly -ResultSize 2000
```