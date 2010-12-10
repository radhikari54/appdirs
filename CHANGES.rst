appdirs Changelog
=================

appdirs 1.2.0 (not yet released)
--------------------------------

- [Unix] Put ``user_log_dir`` under the *cache* dir on Unix. Seems to be more
  typical.
- [issue 9] Make ``unicode`` work on py3k.

appdirs 1.1.0
-------------

- [issue 4] Add ``AppDirs.user_log_dir``.
- [Unix, issue 2, issue 7] appdirs now conforms to `XDG base directory spec
  <http://standards.freedesktop.org/basedir-spec/basedir-spec-latest.html>`_.
- [Mac, issue 5] Fix ``site_data_dir()`` on Mac.
- [Mac] Drop use of 'Carbon' module in favour of hardcoded paths; supports
  Python3 now.
- [Windows] Append "Cache" to ``user_cache_dir`` on Windows by default. Use
  ``opinion=False`` option to disable this.
- Add ``appdirs.AppDirs`` convenience class. Usage:

        >>> dirs = AppDirs("SuperApp", "Acme", version="1.0")
        >>> dirs.user_data_dir
        '/Users/trentm/Library/Application Support/SuperApp/1.0'

- [Windows] Cherry-pick Komodo's change to downgrade paths to the Windows short
  paths if there are high bit chars.
- [Linux] Change default ``user_cache_dir()`` on Linux to be singular, e.g.
  "~/.superapp/cache".
- [Windows] Add ``roaming`` option to ``user_data_dir()`` (for use on Windows only)
  and change the default ``user_data_dir`` behaviour to use a *non*-roaming
  profile dir (``CSIDL_LOCAL_APPDATA`` instead of ``CSIDL_APPDATA``). Why? Because
  a large roaming profile can cause login speed issues. The "only syncs on
  logout" behaviour can cause surprises in appdata info.


appdirs 1.0.1 (never released)
------------------------------

Started this changelog 27 July 2010. Before that this module originated in the
`Komodo <http://www.activestate.com/komodo>`_ product as ``applib.py`` and then
as `applib/location.py
<http://github.com/ActiveState/applib/blob/master/applib/location.py>`_ (used by
`PyPM <http://code.activestate.com/pypm/>`_ in `ActivePython
<http://www.activestate.com/activepython>`_). This is basically a fork of
applib.py 1.0.1 and applib/location.py 1.0.1.
