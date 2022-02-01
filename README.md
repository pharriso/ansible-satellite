Ansible Satellite Examples
=========

Using curl to test API
------------

API docs available on the Satellite server:

https://satellite.example.com/apidoc/v2

For example to search for a content view:

curl -v -H "Content-Type:application/json" -X GET -u admin https://satellite.example.com/katello/api/content_views?search=rhel7 | python -m json.tool

To update an entry. This updates content view associated to a content host:

curl -v -H "Content-Type:application/json" -X PUT -u admin -d '{"host": {"content_facet_attributes": {"content_view_id": "11"}}}' https://satellite.example.com/api/v2/hosts/1726 | python -m json.tool
