# ordplayground

A regtest playground to have a dev enviroment to test out inscriptions incribing and running the ord explorer in regtest

- [x] Bitcoin binary running in docker
- [ ] Ord binary running in docker
- [ ] Regtest shell script
- [ ] Example inscribe shell script
- [ ] Running ord server in regtest for viewing

## RegTest 

The point of this repo is to take the following commands that will create a 
bitcoin/ord regtest and make it easy to recreate in a docker enviroment for 
Inscription development

```
bitcoind -regtest -txindex
ord -r wallet create
ord -r wallet receive
bitcoin-cli -regtest generatetoaddress 101 <receiveAddress>
ord -r wallet balance
ord -r wallet inscribe <file> --fee-rate 1
bitcoin-cli -regtest generatetoaddress 1 <receiveAddress>
ord -r server
```
navigate to localhost:80
