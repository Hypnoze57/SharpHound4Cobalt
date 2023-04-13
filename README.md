---
SharpHound Open Source Client version: 1.0.4
---

# SharpHound4Cobalt

## Integration with Cobalt

The SharpHound data (test file, json, zip, cache file) will not be written on the disk but only sent to Cobalt Strike downloads through [BOF.NET](https://github.com/CCob/BOF.NET) library.

Thus, you must run it with Cobalt `bofnet` command otherwise the ingestor data will be lost.

Only individual JSON files will be sent as it was the easiest way to keep this working on 'big' AD.

## Usage

All the options remain the same except those related to the ZIP file as they are not anymore relevant.
```
bofnet_init
bofnet_load /path/to/SharpHound4Cobalt.exe
bofnet_execute Sharphound.CobaltRunner -c All,GPOLocalGroup
```

## Credits

[Williamknows](https://williamknowles.io/fetching-sharphound-data-entirely-in-memory-no-dropped-zip-or-json-files-using-bof-net-and-cobalt-strike/)
[CCob](https://github.com/CCob/BOF.NET)


# SharpHound

![GitHub all releases](https://img.shields.io/github/downloads/BloodHoundAD/SharpHound/total)

## Get SharpHound

The latest build of SharpHound will always be in the BloodHound repository [here](https://github.com/BloodHoundAD/BloodHound/tree/master/Collectors)

## Compile Instructions

To build this project, use .net 5.0 and run the following:

```
dotnet restore .
dotnet build
```

## Requirements

SharpHound is designed targeting .Net 4.6.2. SharpHound must be run from the context of a domain user, either directly through a logon or through another method such as RUNAS.


# SharpHound

```csharp
dotnet restore .
dotnet build
```

# CLI
```
  -c, --collectionmethods    (Default: Default) Collection Methods: Container, Group, LocalGroup, GPOLocalGroup,
                             Session, LoggedOn, ObjectProps, ACL, ComputerOnly, Trusts, Default, RDP, DCOM, DCOnly

  -d, --domain               Specify domain to enumerate

  -s, --searchforest         (Default: false) Search all available domains in the forest

  --stealth                  Stealth Collection (Prefer DCOnly whenever possible!)

  -f                         Add an LDAP filter to the pregenerated filter.

  --distinguishedname        Base DistinguishedName to start the LDAP search at

  --computerfile             Path to file containing computer names to enumerate

  --outputdirectory          (Default: .) Directory to output file too

  --outputprefix             String to prepend to output file names

  --cachename                Filename for cache (Defaults to a machine specific identifier)

  --memcache                 Keep cache in memory and don't write to disk

  --rebuildcache             (Default: false) Rebuild cache and remove all entries

  --randomfilenames          (Default: false) Use random filenames for output

  --zipfilename              Filename for the zip

  --nozip                    (Default: false) Don't zip files

  --trackcomputercalls       (Default: false) Adds a CSV tracking requests to computers

  --zippassword              Password protects the zip with the specified password

  --prettyprint              (Default: false) Pretty print JSON

  --ldapusername             Username for LDAP

  --ldappassword             Password for LDAP

  --domaincontroller         Override domain controller to pull LDAP from. This option can result in data loss

  --ldapport                 (Default: 0) Override port for LDAP

  --secureldap               (Default: false) Connect to LDAP SSL instead of regular LDAP

  --disablecertverification  (Default: false) Disable certificate verification for secure LDAP

  --disablesigning           (Default: false) Disables Kerberos Signing/Sealing

  --skipportcheck            (Default: false) Skip checking if 445 is open

  --portchecktimeout         (Default: 500) Timeout for port checks in milliseconds

  --skippasswordcheck        (Default: false) Skip PwdLastSet age check when checking computers

  --excludedcs               (Default: false) Exclude domain controllers from session/localgroup enumeration (mostly for
                             ATA/ATP)

  --throttle                 Add a delay after computer requests in milliseconds

  --jitter                   Add jitter to throttle (percent)

  --threads                  (Default: 50) Number of threads to run enumeration with

  --skipregistryloggedon     Skip registry session enumeration

  --overrideusername         Override the username to filter for NetSessionEnum

  --realdnsname              Override DNS suffix for API calls

  --collectallproperties     Collect all LDAP properties from objects

  -l, --Loop                 Loop computer collection

  --loopduration             Loop duration (Defaults to 2 hours - 00:02:00)

  --loopinterval             Add delay between loops (Example - 00:00:01 is 1 minute)

  --statusinterval           (Default: 30000) Interval in which to display status in milliseconds

  -v                         (Default: 2) Enable verbose output. Lower is more verbose

  --help                     Display this help screen.

  --version                  Display version information.
```
