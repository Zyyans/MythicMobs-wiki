Mechanic: Set Rotation
======================

Changes the rotation of the target.

Attributes
----------

| Attribute | Aliases | Description                                      | Default Value |
|-----------|---------|--------------------------------------------------|---------------|
| relative  |         | If the change is relative to the target, boolean |               |
| yaw       |         | The new yaw                                      | 0             |
| pitch     |         | The new pitch                                    | 0             |

  

Examples
--------

      Skills:
      - setrotation{relative=true;pitch=-45}
      - ...
