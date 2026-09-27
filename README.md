# Kustom Substitution Scraper

Scrape school substitution data and display it in any Kustom widget or wallpaper.

- The official site is slow to load.
- The official site is visually cluttered.
- The official site buries the useful info under a lot of noise.

Use this script to easily fetch substitution data for you class!

## Index

- [Requirements](#requirements)
- [Script usage](#usage)
- [Flow usage explanation](#why-use-flow)
- [Contribution](#contribution)


<img src="assets/preview.png" alt="Widget preview" width="300">

## Requirements

- Kustom KWGT or KLWP with `sh` and `tc(reg...)` support.
- `curl` command available on device.
- Network access to access [school's EduPage server](https://smjkcpagi.edupage.org/substitution).

## Usage

1. Copy the content of `main.kode`
2. Paste the text into a [flow](#why-use-flow) formula
3. You can configure your class by editing the class local variable
```
lv("class","5S1" <--- Edit your class here)+ 
lv("date",df(yyyy-MM-dd))+
```
example
```
lv("class","3 ADIL")+ 
lv("date",df(yyyy-MM-dd))+
```
4. The script returns nothings when there is no substitution for the day
5. _(Optional)_ Use the `translate.kode` to have the data return in English

## Why use flow

1. **Rate limiting.** The script sends new request to the [school's EduPage server](https://smjkcpagi.edupage.org/substitution). Frequent requests may get your device temporarily blocked. 
2. **Battery drain.** A network request on each tick keeps the radio on and drains the battery quickly.
3. **Network usage.** Each fetch is ~14 KB. Network usage adds up across a day on each widget refresh.

A Flow decouples the fetch from the display: the data is fetched only when you trigger it, and the widget simply reads the cached result.

## Contribution

Contributions are welcome. You can:
- Open a new issue for suggestions or bug report
- Open a pull request on GitHub.
- Email a patch to **rowen778623@gmail.com**.
