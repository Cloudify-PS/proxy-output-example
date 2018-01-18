# proxy-output-example
Create and install a deployment from the proxy-test.yaml blueprint.

Example:

Node-instance details:
```bash
[centos@cfy-cli proxy]$ cfy node-instances list
Listing all instances...

Node-instances:
+---------------------+---------------+---------+--------------+---------+--------------+----------------+------------+
|          id         | deployment_id | host_id |   node_id    |  state  | availability |  tenant_name   | created_by |
+---------------------+---------------+---------+--------------+---------+--------------+----------------+------------+
| proxy_output_dlcslp |   proxy-test  |         | proxy_output | started |    tenant    | default_tenant |   admin    |
|   test_node_49dcxm  |  proxy-output |         |  test_node   | started |    tenant    | default_tenant |   admin    |
+---------------------+---------------+---------+--------------+---------+--------------+----------------+------------+

[centos@cfy-cli proxy]$ cfy node-instances get proxy_output_dlcslp
Retrieving node instance proxy_output_dlcslp

Node-instance:
+---------------------+---------------+---------+--------------+---------+--------------+----------------+------------+
|          id         | deployment_id | host_id |   node_id    |  state  | availability |  tenant_name   | created_by |
+---------------------+---------------+---------+--------------+---------+--------------+----------------+------------+
| proxy_output_dlcslp |   proxy-test  |         | proxy_output | started |    tenant    | default_tenant |   admin    |
+---------------------+---------------+---------+--------------+---------+--------------+----------------+------------+

Instance runtime properties:
        blueprint: {'application_file_name': 'proxy-output.yaml', 'id': 'proxy-output', 'blueprint_archive': 'https://github.com/Cloudify-PS/proxy-output-example/archive/master.zip'}
        executions: {'workflow_id': 'install'}
        deployment: {'outputs': {'out_test1': 'test_1', 'out_test2': {'prop_test2': 'test_2'}}, 'id': 'proxy-output'}
```

Output:
```bash
[centos@cfy-cli proxy]$ cfy deployments outputs proxy-test
Retrieving outputs for deployment proxy-test...
 - "proxy_out_test2":
     Description: Example of proxy output
     Value: {u'prop_test2': u'test_2'}
 - "proxy_out_test1":
     Description: Example of proxy output
     Value: test_1
```
