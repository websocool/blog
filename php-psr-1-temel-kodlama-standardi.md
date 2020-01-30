# PSR-1: Temel Kodlama Standardı

PSR-1 standardı, birlikte çalışılabilirliği sağlamak için teknik olarak kodlama standartlarını belirlememizi sağlar.

---

## Genel bakış

- PHP dosyalarınızda sadece `<?php` ya da `<?=` etiketleri kullanılmalıdır.
- Kodlarınız `UTF-8 Bomsuz` olarak yazılmalıdır.
- Kodlarınız ya tanımlardan (sınıf, fonksiyon, sabit vb.) ya da yan etiketlerden (çıktı, .ini değişikliği vb.) oluşmalıdır. İkisi birden olmamalıdır.
- Namespace ve Sınıf'lar `PSR-4` standardını takip etmelidir.
- Sınıf isimleri `StudlyCaps` olarak yazılmalıdır. Yani her kelimenin baş harfi büyük olacak şekilde.
- Sınıf sabitleri büyük harflerle ve alt çizgi ile ayrılacak şekilde tanımlanmalıdır.
- Metod isimleri `camelCase` olarak tanımlanmalıdır. Yani ilk kelimenin baş harfi küçük, diğer kelimelerin baş harfleri büyü kolacak şekilde.

---

## Dosyalar

---

### PHP Etiketleri

Ya uzun `<?php ?>` kodları ya da kısa `<?= ?>` kodları kullanılmalıdır. Ancak ikisi aynı anda kullanılmamalıdır.

---

### Karakter Kodlaması

UTF-8 bomsuz olmalıdır.

---

### Yan Etkiler

Bir dosya içerisinde hem tanımlar hem de yan etkiye bağlı kodlamalar yapılmamalıdır.

Aşağıdaki örnek, uyulmaması gereken yanlış bir örnektir.

```php
// yan etki: ini ayarını değiştirme
ini_set('error_reporting', E_ALL);

// yan etki: dosya yükleme
include "file.php";

// yan etki: çıktı
echo "<html>\n";

// tanım
function foo()
{
    // fonksiyon içeriği
}
```

Aşağıdaki örnek, uyulması gereken doğru bir örnektir.

```php
<?php
// tanım
function foo()
{
    // fonksiyon içeriği
}

// koşullu tanımlar kabul görür, sorun yoktur
if (! function_exists('bar')) {
    function bar()
    {
        // fonksiyon içeriği
    }
}
```

---

## Namespace ve Sınıflar

Namespace'ler ve sınıflar PSR-4 standardını takip etmelidir.

Bu da her sınıfın ayrı dosyalarda olması gerektiği ve her birisinin namespace'lerinin en az bir üst klasörü temsil etmesi gerektiği anlamına gelir.

Sınıf isimleri `StudlyCaps` olarak tanımlanmalıdır. Yani her kelimenin ilk harfi büyük olacak şekilde.

PHP 5.3 ve sonrası için namespace tanımları şu şekilde yapılmalıdır;

```php
<?php
namespace Vendor\Model;

class Foo
{
}
```

PHP 5.2.x ve öncesi için ise kullanım prefix'ler şeklinde olmalıdır;

```php
<?php
class Vendor_Model_Foo
{
}
```

---

## Sınıf sabitleri, Özellikler ve Metodlar

Sınıf ifadesi tüm sınıfları, interface'leri ve trait'leri kapsamaktadır.

---

### Sabitler

Sabitler, tamamı büyük olacak şekilde ve kelimeler arası alt tire ile yazılacak şekilde tanımlanmalıdır.

```php
<?php
namespace Vendor\Model;

class Foo
{
    const VERSION = '1.0';
    const DATE_APPROVED = '2012-06-01';
}
```

---

### Özellikler

Bu standart, özelliklerin kullanımıyla ilgili bir önerme içermez. `$StudlyCaps`, `$camelCase` ya da `$under_score` adlandırma kurallarından birisi kullanılabilir.

Ancak hangi adlandırma kuralı kullanılırsa kullanılsın, makul bir kapsamda tutarlı bir şekilde uygulanmalıdır. İsimlendirmeler vendor seviyesinde, paket seviyesinde, sınıf seviyesinde ya da metod seviyesinde olabilir.

---

### Metodlar

Metod isimleri `camelCase()` olarak tanımlanmalıdır. Yani ilk kelimenin baş harfi küçük, diğer kelimelerin ilk harfi büyük olacak şekilde tanımlanmalıdır.
