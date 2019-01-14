# i3-qubes
i3-gaps 4.12 for Qubes OS 3.2 (*Qubes 4.x build soon!*)

# Building & installing

**buildvm:**
*Note: buildvm must be running the same version of Fedora as dom0*

    dnf groupinstall "Development Tools" "Development Libraries"
    git clone https://github.com/unendingPattern/i3-gaps-qubes i3-gaps-qubes
    wget https://github.com/Airblader/i3/archive/4.12.tar.gz -O i3-gaps-qubes/i3/i3-4.12.tar.gz
    gunzip < i3-gaps-qubes/i3/i3-4.12.tar.gz | bzip2 > i3-gaps-qubes/i3/i3-4.12.tar.bz2

    cd i3-gaps-qubes
    dnf install -y $(cat build-deps.list)
    make rpms

**dom0:**

    qvm-run --pass-io buildvm-f2x 'cat /home/user/i3-gaps-qubes/rpm/x86_64/i3-4*.rpm' > i3.rpm
    sudo dnf install i3.rpm

## Contributors
https://github.com/unendingPattern
https://github.com/SietsevanderMolen
https://github.com/o-
https://github.com/minad
