###### Help ###################################################################

help:
	@echo '    vendor .................................... installs dependencies'
	@echo '    vendor-update ............................. updates dependencies'
	@echo '    go-vet .................................... runs go vet in source code'
	@echo '    test ...................................... runs test'

###### Dependencies ###########################################################

vendor:
	go mod vendor

vendor-update:
	go get -u ./..
	go mod tidy
	go mod vendor

###### Tools ###############################################################

go-vet:
	go vet `go list ./... | grep -v vendor`

test:
	ginkgo -v --trace -randomizeSuites=true -randomizeAllSpecs=true -keepGoing=true -failOnPending tests
