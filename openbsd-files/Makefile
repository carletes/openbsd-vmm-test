all: \
	/etc/dhcpd.conf \
	/etc/hostname.bridge0 \
	/etc/hostname.vether0 \
	/etc/pf.conf \
	/etc/profile \
	/etc/rc.conf.local \
	/etc/sysctl.conf \
	/etc/vm.conf

/etc/dhcpd.conf: dhcpd.conf
	cp dhcpd.conf $@
	chown root: $@
	rcctl stop dhcpd
	rcctl start dhcpd

/etc/hostname.bridge0: hostname.bridge0
	cp hostname.bridge0 $@
	chown root: $@
	sh /etc/netstart bridge0

/etc/hostname.vether0: hostname.vether0
	cp hostname.vether0 $@
	chown root: $@
	sh /etc/netstart vether0

/etc/pf.conf: pf.conf
	cp pf.conf $@
	chown root: $@
	chmod 0600 $@
	pfctl -f $@

/etc/profile: profile
	cp profile $@
	chown root: $@

/etc/rc.conf.local: rc.conf.local
	cp rc.conf.local $@
	chown root: $@

/etc/sysctl.conf: sysctl.conf
	cp sysctl.conf $@
	chown root: $@

/etc/vm.conf: vm.conf
	cp vm.conf $@
	chown root: $@
	vmctl reload
