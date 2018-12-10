# iBot 3000
## Pasyvios pozicijų stebėsenos algoritmas (botas)



### Įžanga

2018 prasidėjo kripto valiutų burbulo nuosmukis. Nemaža dalis `low cap` valiutų prarado iki 99% savo `ath` vertės. Bendra kapitalizacija susitraukė nuo 800mlrd. iki 125mlrd. 

Vienintelė grandis, kuri iki šiol nepraranda pajamų yra biržos `exchange`. Tokios kompanijos kaip `Kraken`, `Bitfinex` ar `BitMEX`sėkmingai augina darbuotojų skaičių, tobulina turimas prekybos platformas ir didina apyvartą. Nemažą dalį jos sudaro prekybos komisiniai, atidarytos `Long/Short` pozicijos ir jų laikymas `margin fees`.

Biržos taip pat atlieka ir `market maker`vaidmenį didindamos bendrą likvidumą. Iš čia ir kyla problema ir kartu jos sprendimas.


## Problema

`Market maker` užsiima reguliariu `SL hunt` ir `order book`pravalymu. Nereguliuojamoje rinkoje tai įprastas procesas. O pakilimo laikotarpiu buvęs funkcionalumas `trailing stop-loss` atjungtas kaip per daug prekybos platformą apkraunantis funckionalumas. 

---


# Sprendimas


„Web based“ botas, veikiantis kaip pasyvus biržos stebėsenos įrankis galintis atlikti tris funkcijas:

1. Realiu laiku atvaizduoti atidarytas pozicijas ir esminę jų informaciją:
    * `Position size`
    * `P/L`
    * `Roll over fees` 
    * `Exposure time`
    * `Current Spred`

2. Realiu laiku sukurti ir įvykdyti TP/SL poziciją esant tinkamoms iš anksto apibrėžtoms sąlygoms:
    * `Spike` atsižvelgiant į laiko ir kainos pokyčio intervalą sugeneruoti TP/SL poziciją
    * `Volume` 
    * `RSI` 

3. Nustatytais laiko intervalais sekti esminius prekybos pokyčius:
    * `Volume` pokytį
    * `RSI` pokytį (reikšmę >30 <80)
    * `Pivot` support/resistance 
    * `Longs/Shorts` absoliučią reikšmę ir santykį

# Turimi įrankiai ir informacija
[Kraken Exchange](http:/kraken.com)

[Python3 API](https://github.com/veox/python3-krakenex)




<!--***

* asd asd
+ asdasd
- asdasd
    * asd
-->

Pavyzdinės `market maker` arba `liquidations` situacijos:

![Example 1](http://buro.lt/_storage/pyth/p1.jpg)

![Example 2](http://buro.lt/_storage/pyth/p2.jpg)

