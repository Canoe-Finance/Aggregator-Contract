# MetaDEx Contract

![Architecture](https://user-images.githubusercontent.com/35088567/149532852-f5fc64a8-9eb2-410c-8cbd-f45e56c9ee96.png)

- When user open the Dex web page,the page will call "AMM Exchange Rate Collector" contract's view method without gas and sign. The frontend will get exchange rate of AMMs therefore.Then,the web page will calculate the best routine within browser by webassembly code. Once the front page get the proper routine, the web page will call "AMM Routine Worker" contract and implement the refined routine.The "AMM Routine Worker" contract will call "AMM adapter",the lib contract,and complete exchange eventually.

- The adapter of AMMs can be modified,add ,and removed flexibly and users' assets will not be affected at all. "MetaDex Routine Refiner" is made by rust which can run in browser more efficiently. Generally, the backend servers provide statistics only. It's not necessary to connect backend servers when users intend to make exchanges with exact trading pair.

- MetaDex provides a function, wthich user can use and have rutine imlplements partially if another part(s) can not fit the slipping rate limit.
