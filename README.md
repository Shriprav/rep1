# rep1
$actionUrl = "http://spwfe/sites/team"
$site = [Microsoft.SharePoint.SPSite]::new($actionUrl)
$site | FL
Write-Host "Site.ContentDatabase.IsReadyOnly:" $site.ContentDatabase.IsReadOnly
$webExactMatch = $site.OpenWeb($actionUrl, $true)
if($webExactMatch -ne $null)
{
    write-Host "WebExactMatch language: " $webExactMatch.Language
}
else
{
    write-host "webExactMatch is null"
}
