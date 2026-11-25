# Angular CLI ile Esri (ArcGIS JS) Harita Örneği

Angular CLI ile oluşturulmuş bir projeye `esri-loader` kullanarak ArcGIS API for JavaScript haritası
yerleştirmeyi gösteren örnek. Esri'nin `angular-cli-esri-map` örneği temel alınmıştır.

> **Not:** Bu depo 2018 yılında eğitim/örnek amaçlı yazıldı ve artık güncellenmiyor. Bağımlılıkları eskidir ve
> bilinen güvenlik açıkları içerir; üretimde kullanmayın.

## İçerik

Proje `example1` klasöründedir.

- `src/app/esri-map/` — `EsriMapComponent`: `esri-loader` ile `esri/Map` ve `esri/views/MapView`
  modüllerini yükler, haritayı bileşendeki `div`'e çizer. Yakınlaştırma, merkez ve altlık harita (`basemap`)
  `@Input` ile değiştirilebilir; harita yüklenince `mapLoaded` olayı yayınlanır.
- `src/app/app.component.html` — yalnızca `<app-esri-map>` etiketini içerir.
- `example1/README.md` — paketlerin kurulumu ve bileşenin eklenmesiyle ilgili ders notları.

## Teknolojiler

- Angular 7.0, Angular CLI 7.0.6, TypeScript 3.1
- `esri-loader` 2.5, `@types/arcgis-js-api` 4.9
- Harita stili ArcGIS JS API 4.6 CSS'inden (js.arcgis.com) yüklenir.

## Çalıştırma

Depoda Angular CLI'ın ürettiği bazı dosyalar eksiktir: kökteki `tsconfig.json`, `tslint.json` ve `e2e/`
klasörü, ayrıca `package-lock.json`. Bu yüzden proje olduğu gibi derlenmez. En kolay yol:

1. Node.js'in Angular 7 ile uyumlu eski bir sürümüyle (örneğin 10.x) `ng new` ile yeni bir proje oluşturun.
2. `npm install --save esri-loader @types/arcgis-js-api` ile paketleri kurun.
3. Bu depodaki `example1/src/app` içeriğini yeni projeye kopyalayın ve `tsconfig.app.json` ile
   `tsconfig.spec.json` dosyalarına `"types": ["arcgis-js-api"]` ekleyin.
4. `npm start` (ya da `ng serve`) ile çalıştırıp `http://localhost:4200` adresini açın.
