## Log khi khởi tạo volume

```
2020-09-15 08:02:43.963 23473 INFO cinder.volume.flows.manager.create_volume [req-aa762658-802e-4c4c-8efa-4b11611b2360 16d493f9bfe741018b610876c18fc00b e4ada57c6bd0464eaaff54fa49d57ad3 - default default] Volume d3de1c70-b099-47db-9493-f594a1409bb4: being created as image with specification: {'status': u'creating', 'image_location': (None, None), 'volume_size': 2, 'volume_name': u'volume-d3de1c70-b099-47db-9493-f594a1409bb4', 'image_id': u'1cb8813d-43dd-426a-a787-d96acd175092', 'image_service': <cinder.image.glance.GlanceImageService object at 0x7f73f467c290>, 'image_meta': {u'status': u'active', u'file': u'/v2/images/1cb8813d-43dd-426a-a787-d96acd175092/file', u'id': u'1cb8813d-43dd-426a-a787-d96acd175092', u'name': u'cirros', u'tags': [], u'container_format': u'bare', u'created_at': datetime.datetime(2020, 9, 8, 7, 16, 45, tzinfo=<iso8601.Utc>), u'disk_format': u'qcow2', u'updated_at': datetime.datetime(2020, 9, 8, 7, 16, 45, tzinfo=<iso8601.Utc>), u'visibility': u'public', u'os_hash_algo': u'sha512', u'owner': u'e4ada57c6bd0464eaaff54fa49d57ad3', u'protected': False, u'os_hash_value': u'6513f21e44aa3da349f248188a44bc304a3653a04122d8fb4535423c8e1d14cd6a153f735bb0982e2161b5b5186106570c17a9e58b64dd39390617cd5a350f78', u'min_ram': 0, u'checksum': u'443b7623e27ecf03dc9e01ee93f67afe', u'min_disk': 0, u'os_hidden': False, u'virtual_size': None, 'properties': {}, u'size': 12716032}}

2020-09-15 08:02:44.354 23473 INFO cinder.image.image_utils [req-aa762658-802e-4c4c-8efa-4b11611b2360 16d493f9bfe741018b610876c18fc00b e4ada57c6bd0464eaaff54fa49d57ad3 - default default] Image download 12.00 MB at 12.00 MB/s

2020-09-15 08:02:49.833 23473 INFO cinder.image.image_utils [req-aa762658-802e-4c4c-8efa-4b11611b2360 16d493f9bfe741018b610876c18fc00b e4ada57c6bd0464eaaff54fa49d57ad3 - default default] Converted 44.00 MB image at 44.00 MB/s

2020-09-15 08:02:49.971 23473 INFO cinder.volume.flows.manager.create_volume [req-aa762658-802e-4c4c-8efa-4b11611b2360 16d493f9bfe741018b610876c18fc00b e4ada57c6bd0464eaaff54fa49d57ad3 - default default] Volume volume-d3de1c70-b099-47db-9493-f594a1409bb4 (d3de1c70-b099-47db-9493-f594a1409bb4): created successfully

2020-09-15 08:02:49.992 23473 INFO cinder.volume.manager [req-aa762658-802e-4c4c-8efa-4b11611b2360 16d493f9bfe741018b610876c18fc00b e4ada57c6bd0464eaaff54fa49d57ad3 - default default] Created volume successfully.
```

## Gán Volume cho VM

```
2020-09-15 08:34:40.404 23473 INFO cinder.volume.targets.lio [req-6a677942-9d46-42e8-8ca3-33fe438c8918 16d493f9bfe741018b610876c18fc00b e4ada57c6bd0464eaaff54fa49d57ad3 - default default] Creating iscsi_target for volume: volume-d3de1c70-b099-47db-9493-f594a1409bb4
2020-09-15 08:34:45.223 23473 INFO cinder.volume.manager [req-6a677942-9d46-42e8-8ca3-33fe438c8918 16d493f9bfe741018b610876c18fc00b e4ada57c6bd0464eaaff54fa49d57ad3 - default default] attachment_update completed successfully.
```

## Log detach volume

```
2020-09-15 08:44:00.916 23473 INFO cinder.volume.manager [req-6e930f39-a0b4-45a9-bdc2-c363f9485fb0 16d493f9bfe741018b610876c18fc00b e4ada57c6bd0464eaaff54fa49d57ad3 - default default] Terminate volume connection completed successfully.
2020-09-15 08:44:01.780 23473 INFO cinder.volume.targets.lio [req-6e930f39-a0b4-45a9-bdc2-c363f9485fb0 16d493f9bfe741018b610876c18fc00b e4ada57c6bd0464eaaff54fa49d57ad3 - default default] Removing iscsi_target: 906cc170-c941-42fa-9bc3-50d6065bbad3
```

## Xóa volume

```
2020-09-15 09:45:29.792 23473 INFO cinder.volume.targets.iscsi [req-3a2ff057-9601-4dbd-ba6a-5e2500ac958d 16d493f9bfe741018b610876c18fc00b e4ada57c6bd0464eaaff54fa49d57ad3 - default default] Skipping remove_export. No iscsi_target is presently exported for volume: 906cc170-c941-42fa-9bc3-50d6065bbad3
2020-09-15 09:45:31.640 23473 INFO cinder.volume.drivers.lvm [req-3a2ff057-9601-4dbd-ba6a-5e2500ac958d 16d493f9bfe741018b610876c18fc00b e4ada57c6bd0464eaaff54fa49d57ad3 - default default] Successfully deleted volume: 906cc170-c941-42fa-9bc3-50d6065bbad3
2020-09-15 09:45:34.337 23473 INFO cinder.volume.manager [req-3a2ff057-9601-4dbd-ba6a-5e2500ac958d 16d493f9bfe741018b610876c18fc00b e4ada57c6bd0464eaaff54fa49d57ad3 - default default] Deleted volume successfully.
```

