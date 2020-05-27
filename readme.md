

## List all folders and their sizes

    gci -force 'C:\Users'-ErrorAction SilentlyContinue | ? { $_ -is [io.directoryinfo] } | % {
    $len = 0
    gci -recurse -force $_.fullname -ErrorAction SilentlyContinue | % { $len += $_.length }
    $_.fullname, '{0:N2} GB' -f ($len / 1Gb)
    }

from http://woshub.com/powershell-get-folder-sizes/
