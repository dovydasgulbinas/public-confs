CSGO_CONF=autoexec.cfg
OSX_CFG_DIR=~/Library/ApplicationSupport/Steam/steamapps/common/Counter-Strike\ Global\ Offensive/csgo/cfg

AUTOEXEC_DST="$(OSX_CFG_DIR)/autoexec.cfg"

DATE=$(shell date +'%y_%m_%d_%H_%M_%S')

edit:
	vim $(CSGO_CONF)

confdir-osx:
	open $(OSX_CFG_DIR)

copy-conf-osx:
	# mv  $(AUTOEXEC_DST) $(AUTOEXEC_DST)_$(DATE)
	cp ./autoexec.cfg "$(AUTOEXEC_DST)"

backup-osx:
	mv -v $(AUTOEXEC_DST) $(AUTOEXEC_DST)_$(DATE) || true

init-osx: backup-osx
	chmod 751 autoexec.cfg
	ln $(CSGO_CONF) $(OSX_CFG_DIR)/autoexec.cfg
	ls -alt $(OSX_CFG_DIR)/autoexec.cfg

date:
	@echo $(DATE)
	@echo $(AUTOEXEC_DST)

ls:
	ls -alt $(OSX_CFG_DIR)

open:
	open $(OSX_CFG_DIR)

diff:
	vimdiff autoexec.cfg "$(AUTOEXEC_DST)"

build-for-cmd:
	awk -F '//' '{print $1}' autoexec.cfg | sed '/^$/d' | sed -z 's/\n/;/g'