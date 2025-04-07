# World countries in JSON, CSV, XML and YAML.

[![License](https://img.shields.io/packagist/l/mledoze/countries.svg?style=flat)](https://opendatacommons.org/licenses/odbl/1.0/)


## Countries data
This repository contains a list of world countries, as defined by [ISO Standard 3166-1](https://en.wikipedia.org/wiki/ISO_3166-1),
in JSON, CSV, XML and YAML. **Warning:** not all entities in this project are independent countries; refer to the `independent` property to know if the country is considered a sovereign state.

Each line contains the country:

 - `name`
 	 - `common` - common name in english
 	 - `official` - official name in english
 	 - `native` - list of all native names
 	 	- key: three-letter ISO 639-3 language code
	 	- value: name object
	 		- key: `official` - official name translation
	 		- key: `common` - common name translation
 - country code top-level domain (`tld`)
 - code ISO 3166-1 alpha-2 (`cca2`)
 - code ISO 3166-1 numeric (`ccn3`)
 - code ISO 3166-1 alpha-3 (`cca3`)
 - code International Olympic Committee (`cioc`)
 - ISO 3166-1 independence status (`independent`) (denotes the country is considered a sovereign state)
 - ISO 3166-1 assignment status (`status`)
 - UN Member status (`unMember`)
 - [UN Regional Group](https://en.wikipedia.org/wiki/United_Nations_Regional_Groups) (`unRegionalGroup`)
 - `currencies` - list of all currencies
 	- key: ISO 4217 currency code
 	- value: currency object
 		- key: `name` name of the currency
 		- key: `symbol` symbol of the currency
 - International Direct Dialing info (`idd`)
 	- `root` - the root geographical code prefix. e.g. +6 for New Zealand, +4 for UK.
 	- `suffixes` - list of all suffixes assigned to this country. 4 for NZ, 809, 829, and 849 for Dominican Republic.
 - capital city(ies) (`capital`)
 - alternative spellings (`altSpellings`)
 - region
 - subregion
 - list of official languages (`languages`)
 	- key: three-letter ISO 639-3 language code
 	- value: name of the language in english
 - list of name translations (`translations`)
 	- key: three-letter ISO 639-3 language code
 	- value: name object
 		- key: official - official name translation
 		- key: common - common name translation
 - latitude and longitude (`latlng`)
 - `demonyms` - name of residents, translated & genderized
    - key: three-letter ISO 639-3 language code
	- value: genderized demonym object
		- key: `f` (female) or `m` (male)
		- value: genderized demonym translation
 - landlocked status (`landlocked`)
 - land borders (`borders`)
 - land area in km² (`area`)
 - emoji flag (`flag`)
 - calling codes (`callingCodes`)

#### Additional data
The [data](https://github.com/mledoze/countries/tree/master/data) folder contains additional data such as the countries
GeoJSON outlines and flags in SVG format.

## Examples
### JSON
```json
{
	"name": {
		"common": "Austria",
		"official": "Republic of Austria",
		"native": {
			"bar": {
				"official": "Republik Österreich",
				"common": "Österreich"
			}
		}
	},
	"tld": [".at"],
	"cca2": "AT",
	"ccn3": "040",
	"cca3": "AUT",
	"cioc": "AUT",
	"independent": true,
	"status": "officially-assigned",
	"unMember": true,
	"unRegionalGroup": "Western European and Others Group",
	"currencies": {"EUR": {"name": "Euro", "symbol": "\u20ac"}},
	"idd": {
		"root": "+4",
		"suffixes": ["3"]
	},
	"capital": ["Vienna"],
	"altSpellings": ["AT", "Osterreich", "Oesterreich"],
	"region": "Europe",
	"subregion": "Western Europe",
	"languages": {
		"bar": "Austro-Bavarian German"
	},
	"translations": {
		"cym": {"official": "Republic of Austria", "common": "Awstria"},
		"deu": {"official": "Republik Österreich", "common": "Österreich"},
		"fra": {"official": "République d'Autriche", "common": "Autriche"},
		"hrv": {"official": "Republika Austrija", "common": "Austrija"},
		"ita": {"official": "Repubblica d'Austria", "common": "Austria"},
		"jpn": {"official": "オーストリア共和国", "common": "オーストリア"},
		"nld": {"official": "Republiek Oostenrijk", "common": "Oostenrijk"},
		"por": {"official": "República da Áustria", "common": "Áustria"},
		"rus": {"official": "Австрийская Республика", "common": "Австрия"},
		"spa": {"official": "República de Austria", "common": "Austria"}
	},
	"latlng": [47.33333333, 13.33333333],
	"demonyms": {
		"fra": {
			"f": "Autrichienne",
			"m": "Autrichien"
		},
		"spa": {
			"f": "Austriaco",
			"m": "Austriaca"
		}
	},
	"landlocked": true,
	"borders": ["CZE", "DEU", "HUN", "ITA", "LIE", "SVK", "SVN", "CHE"],
	"area": 83871,
	"callingCodes": ["+43"]
	"flag": "\ud83c\udde6\ud83c\uddf9"
}
```

### GeoJSON and TopoJSON outlines
See an example for Germany: [GeoJSON](https://github.com/mledoze/countries/blob/bb61a1cddfefd09ad5c92ad0a1effbfceba39930/data/deu.geo.json) or [TopoJSON](https://github.com/mledoze/countries/blob/442472de98e80f4a44f1028960dbb0dfb1d942fe/data/deu.topo.json).



### XML
```xml
<?xml version="1.0" encoding="UTF-8"?>
<countries>
  <country name.common="Aruba" name.official="Aruba" name.native.nld.official="Aruba" name.native.nld.common="Aruba" name.native.pap.official="Aruba" name.native.pap.common="Aruba" tld=".aw" cca2="AW" ccn3="533" cca3="ABW" cioc="ARU" independent="0" status="officially-assigned" unMember="0" currencies.AWG.name="Aruban florin" currencies.AWG.symbol="ƒ" idd.root="+2" idd.suffixes="97" capital="Oranjestad" altSpellings="AW" region="Americas" subregion="Caribbean" languages.nld="Dutch" languages.pap="Papiamento" translations.ces.official="Aruba" translations.ces.common="Aruba" translations.deu.official="Aruba" translations.deu.common="Aruba" translations.est.official="Aruba" translations.est.common="Aruba" translations.fin.official="Aruba" translations.fin.common="Aruba" translations.fra.official="Aruba" translations.fra.common="Aruba" translations.hrv.official="Aruba" translations.hrv.common="Aruba" translations.hun.official="Aruba" translations.hun.common="Aruba" translations.ita.official="Aruba" translations.ita.common="Aruba" translations.jpn.official="アルバ" translations.jpn.common="アルバ" translations.kor.official="아루바" translations.kor.common="아루바" translations.nld.official="Aruba" translations.nld.common="Aruba" translations.per.official="آروبا" translations.per.common="آروبا" translations.pol.official="Aruba" translations.pol.common="Aruba" translations.por.official="Aruba" translations.por.common="Aruba" translations.rus.official="Аруба" translations.rus.common="Аруба" translations.slk.official="Aruba" translations.slk.common="Aruba" translations.spa.official="Aruba" translations.spa.common="Aruba" translations.swe.official="Aruba" translations.swe.common="Aruba" translations.urd.official="اروبا" translations.urd.common="اروبا" translations.zho.official="阿鲁巴" translations.zho.common="阿鲁巴" latlng="12.5,-69.96666666" landlocked="0" borders="" area="180" flag="🇦🇼" demonyms.eng.f="Aruban" demonyms.eng.m="Aruban" demonyms.fra.f="Arubaise" demonyms.fra.m="Arubais" callingCodes="+297"/>
  <country name.common="Afghanistan" name.official="Islamic Republic of Afghanistan" name.native.prs.official="جمهوری اسلامی افغانستان" name.native.prs.common="افغانستان" name.native.pus.official="د افغانستان اسلامي جمهوریت" name.native.pus.common="افغانستان" name.native.tuk.official="Owganystan Yslam Respublikasy" name.native.tuk.common="Owganystan" tld=".af" cca2="AF" ccn3="004" cca3="AFG" cioc="AFG" independent="1" status="officially-assigned" unMember="1" currencies.AFN.name="Afghan afghani" currencies.AFN.symbol="؋" idd.root="+9" idd.suffixes="3" capital="Kabul" altSpellings="AF,Afġānistān" region="Asia" subregion="Southern Asia" languages.prs="Dari" languages.pus="Pashto" languages.tuk="Turkmen" translations.ces.official="Afghánská islámská republika" translations.ces.common="Afghánistán" translations.deu.official="Islamische Republik Afghanistan" translations.deu.common="Afghanistan" translations.est.official="Afganistani Islamivabariik" translations.est.common="Afganistan" translations.fin.official="Afganistanin islamilainen tasavalta" translations.fin.common="Afganistan" translations.fra.official="République islamique d'Afghanistan" translations.fra.common="Afghanistan" translations.hrv.official="Islamska Republika Afganistan" translations.hrv.common="Afganistan" translations.hun.official="Afganisztáni Iszlám Köztársaság" translations.hun.common="Afganisztán" translations.ita.official="Repubblica islamica dell'Afghanistan" translations.ita.common="Afghanistan" translations.jpn.official="アフガニスタン・イスラム共和国" translations.jpn.common="アフガニスタン" translations.kor.official="아프가니스탄 이슬람 공화국" translations.kor.common="아프가니스탄" translations.nld.official="Islamitische Republiek Afghanistan" translations.nld.common="Afghanistan" translations.per.official="جمهوری اسلامی افغانستان" translations.per.common="افغانستان" translations.pol.official="Islamska Republika Afganistanu" translations.pol.common="Afganistan" translations.por.official="República Islâmica do Afeganistão" translations.por.common="Afeganistão" translations.rus.official="Исламская Республика Афганистан" translations.rus.common="Афганистан" translations.slk.official="Afgánsky islamský štát" translations.slk.common="Afganistan" translations.spa.official="República Islámica de Afganistán" translations.spa.common="Afganistán" translations.swe.official="Islamiska republiken Afghanistan" translations.swe.common="Afghanistan" translations.urd.official="اسلامی جمہوریہ افغانستان" translations.urd.common="افغانستان" translations.zho.official="阿富汗伊斯兰共和国" translations.zho.common="阿富汗" latlng="33,65" landlocked="1" borders="IRN,PAK,TKM,UZB,TJK,CHN" area="652230" flag="🇦🇫" demonyms.eng.f="Afghan" demonyms.eng.m="Afghan" demonyms.fra.f="Afghane" demonyms.fra.m="Afghan" callingCodes="+93"/>
  <country name.common="Angola" name.official="Republic of Angola" name.native.por.official="República de Angola" name.native.por.common="Angola" tld=".ao" cca2="AO" ccn3="024" cca3="AGO" cioc="ANG" independent="1" status="officially-assigned" unMember="1" currencies.AOA.name="Angolan kwanza" currencies.AOA.symbol="Kz" idd.root="+2" idd.suffixes="44" capital="Luanda" altSpellings="AO,República de Angola,ʁɛpublika de an'ɡɔla" region="Africa" subregion="Middle Africa" languages.por="Portuguese" translations.ces.official="Angolská republika" translations.ces.common="Angola" translations.deu.official="Republik Angola" translations.deu.common="Angola" translations.est.official="Angola Vabariik" translations.est.common="Angola" translations.fin.official="Angolan tasavalta" translations.fin.common="Angola" translations.fra.official="République d'Angola" translations.fra.common="Angola" translations.hrv.official="Republika Angola" translations.hrv.common="Angola" translations.hun.official="Angola" translations.hun.common="Angola" translations.ita.official="Repubblica dell'Angola" translations.ita.common="Angola" translations.jpn.official="アンゴラ共和国" translations.jpn.common="アンゴラ" translations.kor.official="앙골라 공화국" translations.kor.common="앙골라" translations.nld.official="Republiek Angola" translations.nld.common="Angola" translations.per.official="جمهوری آنگولا" translations.per.common="آنگولا" translations.pol.official="Republika Angoli" translations.pol.common="Angola" translations.por.official="República de Angola" translations.por.common="Angola" translations.rus.official="Республика Ангола" translations.rus.common="Ангола" translations.slk.official="Angolská republika" translations.slk.common="Angola" translations.spa.official="República de Angola" translations.spa.common="Angola" translations.swe.official="Republiken Angola" translations.swe.common="Angola" translations.urd.official="جمہوریہ انگولہ" translations.urd.common="انگولہ" translations.zho.official="安哥拉共和国" translations.zho.common="安哥拉" latlng="-12.5,18.5" landlocked="0" borders="COG,COD,ZMB,NAM" area="1246700" flag="🇦🇴" demonyms.eng.f="Angolan" demonyms.eng.m="Angolan" demonyms.fra.f="Angolaise" demonyms.fra.m="Angolais" callingCodes="+244"/>
⋮
<countries>
```

## How to contribute?
Please refer to [CONTRIBUTING](https://github.com/mledoze/countries/blob/master/CONTRIBUTING.md).


## Sources
https://www.currency-iso.org/ for currency codes.

Region and subregion are taken from https://github.com/hexorx/countries.

GeoJSON outlines come from http://thematicmapping.org/downloads/world_borders.php.

The rest comes from Wikipedia.

## Credits
Thanks to:
 - @Glazz for his help with country calling codes
 - @hexorx for his work (https://github.com/hexorx/countries)
 - @frederik-jacques for the capital cities
 - @fayer for the population, geolocation, demonym and area data
 - @ancosen for his help with the borders data
 - @herrjemand for country names and various fixes
 - all the contributors: https://github.com/mledoze/countries/graphs/contributors

## License
See [LICENSE](https://github.com/mledoze/countries/blob/master/LICENSE).

Flags are not licensed under the ODbL license; see <https://en.wikipedia.org/wiki/Wikipedia:Copyright_on_emblems> for more information.
