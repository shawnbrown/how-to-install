
Enable RHEL/CentOS Software Collections at Login
================================================

If you want to automatically enable individual RHEL/CentOS Software
Collections for your bash sessions, you can add the following to your
``.bashrc`` file (example enables Python 3.3 and PostgreSQL 9.2):


.. code-block:: bash

    # ------------------------------------------------------------------
    # Define functions to enable SCLs for current session.
    # ------------------------------------------------------------------
    scl_enable() {
        if [[ $X_SCLS != *$1* ]]; then
            . /opt/rh/$1/enable
            export X_SCLS="$1 $X_SCLS"
        fi
    }
    
    scl_show_enabled() {
        echo "Using Software Collections:"
        echo -e "  ${X_SCLS// /\n  }"
    }
    
    # -----------------------------------------------------------------
    # Enable SCLs, display list for user.
    # -----------------------------------------------------------------
    scl_enable python33
    scl_enable postgresql92
    scl_show_enabled


More info here: http://wiki.centos.org/AdditionalResources/Repositories/SCL
