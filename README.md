# Make-A-DC
Create a domain controller and fill it with realistic user objects based on https://randomuser.me/

The script will build a DC and continue running after the required reboot to fill the domain with users. Each component can be run separately.

## Parameters:

`domain` - Specify the name of the domain to create, if left blank the script will use the domain of the localhost. Only required for building a new domain.

`users` - Specify the number of users to create (1-1000)

`co` - Specify the company name to be used in the AD users' profile

`nat` - Specify the nationality of the users you are creating. https://randomuser.me relies on this for correct address formatting. Default value is `US`

## Examples:

`PS C:\>: Make-A-DC.ps1 -users 22`

Creates 22 random user accounts and inserts them into the domain of the localhost the script is running on.

`PS C:\>: Make-A-DC.ps1 -users 18 -co "Apple Computer" -domain "Test.local"`

Creates the `test.local` domain, then creates 18 random user accounts with `Apple Computer` as the Company Name under the `Organization` user attribute.

`PS C:\>: Make-A-DC.ps1 -domain test.local`

Installs the required AD roles on the local machine, creating a DC for the domain `test.local`, but will not create any users.
