# test-Nikhath

import pyudev

context = pyudev.Context()
for device in context.list_devices(subsystem="usb", DEVTYPE="usb_device"):
    serial = device.get("ID_SERIAL_SHORT")
    if serial:
        print(f"{device.get('ID_MODEL', 'Unknown')}: {serial}")
