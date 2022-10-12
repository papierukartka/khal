# steps to reproduce

1. Open ikhal
2. Create a recurring event (one that has at least 2 instances)
    2.1. The recurrence period of the event doesn't matter
3. Remove at least 2 instances of an event
4. Press q to quit ikhal

Actual result:

- First event removed
- Error:

```bash
Traceback (most recent call last):
  File "/home/kks/Documents/projekty/khal/khal/ui/__init__.py", line 1364, in start_pane
    loop.run()
  File "/home/kks/Documents/projekty/khal/venv/lib/python3.10/site-packages/urwid/main_loop.py", line 287, in run
    self._run()
  File "/home/kks/Documents/projekty/khal/venv/lib/python3.10/site-packages/urwid/main_loop.py", line 385, in _run
    self.event_loop.run()
  File "/home/kks/Documents/projekty/khal/venv/lib/python3.10/site-packages/urwid/main_loop.py", line 790, in run
    self._loop()
  File "/home/kks/Documents/projekty/khal/venv/lib/python3.10/site-packages/urwid/main_loop.py", line 827, in _loop
    self._watch_files[fd]()
  File "/home/kks/Documents/projekty/khal/venv/lib/python3.10/site-packages/urwid/raw_display.py", line 416, in <lambda>
    wrapper = lambda: self.parse_input(
  File "/home/kks/Documents/projekty/khal/venv/lib/python3.10/site-packages/urwid/raw_display.py", line 515, in parse_input
    callback(processed, processed_codes)
  File "/home/kks/Documents/projekty/khal/venv/lib/python3.10/site-packages/urwid/main_loop.py", line 412, in _update
    self.process_input(keys)
  File "/home/kks/Documents/projekty/khal/venv/lib/python3.10/site-packages/urwid/main_loop.py", line 519, in process_input
    something_handled |= bool(self.unhandled_input(k))
  File "/home/kks/Documents/projekty/khal/venv/lib/python3.10/site-packages/urwid/main_loop.py", line 565, in unhandled_input
    return self._unhandled_input(input)
  File "/home/kks/Documents/projekty/khal/khal/ui/base.py", line 205, in on_key_press
    self.backtrack()
  File "/home/kks/Documents/projekty/khal/khal/ui/base.py", line 190, in backtrack
    cb(data)
  File "/home/kks/Documents/projekty/khal/khal/ui/__init__.py", line 1118, in cleanup
    self.collection.delete_instance(href, etag, account, rec_id)
  File "/home/kks/Documents/projekty/khal/khal/khalendar/khalendar.py", line 243, in delete_instance
    raise EtagMissmatch()
khal.khalendar.exceptions.EtagMissmatch
```

Expected result:
All selected instances removed
