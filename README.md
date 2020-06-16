# Reproduction Repository for Poetry LICENSES bug

This repository is a minimally-reproducable example created via the following commands:

```console
$ poetry new poetry-licenses-bug
$ mkdir LICENSES
```

To cause the error to happen, do the following:
```console
$ pip  install .
Processing /home/frere76/projects/tests/poetry-licenses-bug
  Installing build dependencies ... done
  Getting requirements to build wheel ... done
    Preparing wheel metadata ... done
Building wheels for collected packages: poetry-licenses-bug
  Building wheel for poetry-licenses-bug (PEP 517) ... error
  ERROR: Command errored out with exit status 1:
   command: /home/frere76/.asdf/installs/python/3.8.3/bin/python3.8 /home/frere76/.asdf/installs/python/3.8.3/lib/python3.8/site-packages/pip/_vendor/pep517/_in_process.py build_wheel /tmp/tmpjwp444l1
       cwd: /tmp/pip-req-build-u5w5jo8u
  Complete output (18 lines):
  Traceback (most recent call last):
    File "/home/frere76/.asdf/installs/python/3.8.3/lib/python3.8/site-packages/pip/_vendor/pep517/_in_process.py", line 280, in <module>
      main()
    File "/home/frere76/.asdf/installs/python/3.8.3/lib/python3.8/site-packages/pip/_vendor/pep517/_in_process.py", line 263, in main
      json_out['return_val'] = hook(**hook_input['kwargs'])
    File "/home/frere76/.asdf/installs/python/3.8.3/lib/python3.8/site-packages/pip/_vendor/pep517/_in_process.py", line 204, in build_wheel
      return _build_backend().build_wheel(wheel_directory, config_settings,
    File "/tmp/pip-build-env-0mpwncyw/overlay/lib/python3.8/site-packages/poetry/masonry/api.py", line 62, in build_wheel
      WheelBuilder.make_in(
    File "/tmp/pip-build-env-0mpwncyw/overlay/lib/python3.8/site-packages/poetry/masonry/builders/wheel.py", line 55, in make_in
      wb.build()
    File "/tmp/pip-build-env-0mpwncyw/overlay/lib/python3.8/site-packages/poetry/masonry/builders/wheel.py", line 82, in build
      self._write_metadata(zip_file)
    File "/tmp/pip-build-env-0mpwncyw/overlay/lib/python3.8/site-packages/poetry/masonry/builders/wheel.py", line 188, in _write_metadata
      self._add_file(wheel, path, "%s/%s" % (self.dist_info, path.name))
    File "/tmp/pip-build-env-0mpwncyw/overlay/lib/python3.8/site-packages/poetry/masonry/builders/wheel.py", line 265, in _add_file
      with open(full_path, "rb") as src:
  IsADirectoryError: [Errno 21] Is a directory: 'LICENSES'
  ----------------------------------------
  ERROR: Failed building wheel for poetry-licenses-bug
Failed to build poetry-licenses-bug
ERROR: Could not build wheels for poetry-licenses-bug which use PEP 517 and cannot be installed directly
```
