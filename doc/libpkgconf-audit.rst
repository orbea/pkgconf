
libpkgconf `audit` module
=========================

The libpkgconf `audit` module contains the functions related to attaching an audit log file
to a ``pkgconf_client_t`` object.

The audit log format is the same as the output generated by the ``PKG_CONFIG_LOG`` environment
variable.

.. c:function:: void pkgconf_audit_set_log(pkgconf_client_t *client, FILE *auditf)

   Sets the audit log file pointer on `client` to `auditf`.
   The callee is responsible for closing any previous log files.

   :param pkgconf_client_t* client: The client object to modify.
   :param FILE* auditf: The file pointer for the already open log file.
   :return: nothing

.. c:function:: void pkgconf_audit_log(pkgconf_client_t *client, const char *format, ...)

   Logs a message to the opened audit log (if any).

   :param pkgconf_client_t* client: The client object the log message is for.
   :param char* format: The format string to use for the log messages.
   :return: nothing

.. c:function:: void pkgconf_audit_log_dependency(pkgconf_client_t *client, const pkgconf_pkg_t *dep, const pkgconf_dependency_t *depnode)

   Convenience function which logs a dependency node to the opened audit log (if any).

   :param pkgconf_client_t* client: The client object the log message is for.
   :param pkgconf_pkg_t* dep: The dependency package object being logged.
   :param pkgconf_dependency_t* depnode: The dependency object itself being logged.
   :return: nothing
