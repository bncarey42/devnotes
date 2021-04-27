# IAM
IAM (Identity and Access Management)
------------------------------------

User, Group and Role Management

Your whole AWS security is there:

*   users
*   groups
*   roles  
     

Root account is the account with which you created your AWS account

Root account should never be used (nor shared)

User must be created with proper permissions

IAM is at the center of AWS

Policies define permissions and are written in JSON

### High level IAM intro

Users - a physical Person

Group - Functions (admin, devops) or Teams (engineering, design) 

contain Users and define levels of access

Roles - only for internal usage within AWS resources (for a machene)

Policies - define Users, Groups, & Roles

*   defined in JSON

#### IAM has a global view

policies are defined across region

IAM has predefined “managed policies” so make definitions easier

Define Users the least amount of permissions possible

### NOTE

Enterprise can integrate their own repository of users with IAM Federation  (eg to connect to AD Groups) 

Identity Federation uses the SAML standard (