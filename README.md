# New WAS Demo - with a Derby DB!

## Quickstart

```bash
# You need to log into OpenShift first
oc login

# Create a new project
oc new-project nu-was-demo

# Clone down the repo
git clone https://github.com/kenmoini/defaultapp

# Apply the YAMLz
oc apply -f defaultapp/openshift/

# Port forward the WAS Admin panel
oc port-forward pod/$(oc get pods -o custom-columns=POD:.metadata.name --no-headers | grep -v '!*deploy') 9043:9043

# Access the Admin panel at https://localhost:9043/ibm/console/logon.jsp with WSadmin / +ng9ScWh
```