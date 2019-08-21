---
title: Строки стран и регионов
ms.date: 11/04/2016
f1_keywords:
- c.strings
helpviewer_keywords:
- country/region strings
ms.assetid: 5baf0ccf-0d9b-40dc-83bd-323705287930
ms.openlocfilehash: 49eb6bc4473d9e54c06c3bf9290f8c3c96640415
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/15/2019
ms.locfileid: "69500248"
---
# <a name="countryregion-strings"></a>строки страны и региона

Строки страны и региона можно объединять со строкой с названием языка для создания спецификации языкового стандарта для функций `setlocale`, `_wsetlocale`, `_create_locale`и `_wcreate_locale` . Список названий стран и регионов, поддерживаемых разными версиями операционной системы Windows, см. в столбцах **Язык**, **Расположение** и **Тег языка** в таблице, которая приведена в [приложении с описанием поведения продукта](https://msdn.microsoft.com/library/cc233982.aspx) в справочнике по идентификаторам кода языка Windows [MS-LCID]. Пример кода для перечисления имен доступных языковых стандартов и связанных значений см. в руководстве по [ многоязыковой поддержке с примером API на основе имени](/windows/win32/intl/nls--name-based-apis-sample).

## <a name="additional-supported-country-and-region-strings"></a>Дополнительные поддерживаемые строки страны и региона

Реализация библиотеки времени выполнения C от Майкрософт также поддерживает следующие дополнительные строки и аббревиатуры стран и регионов:

|Строка страны или региона|Сокращение|Соответствующее название языкового стандарта|
|----------------------------|------------------|----------------------------|
|america|USA|en-US|
|britain|GBR|en-GB|
|china|CHN|zh-CN|
|czech|CZE|cs-CZ|
|england|GBR|en-GB|
|great britain|GBR|en-GB|
|holland|NLD|nl-NL|
|hong-kong|HKG|zh-HK|
|new-zealand|NZL|en-NZ|
|nz|NZL|en-NZ|
|pr china|CHN|zh-CN|
|pr-china|CHN|zh-CN|
|puerto-rico|PRI|es-PR|
|slovak|SVK|sk-SK|
|south africa|ZAF|af-ZA|
|south korea|KOR|ko-KR|
|south-africa|ZAF|af-ZA|
|south-korea|KOR|ko-KR|
|trinidad & tobago|TTO|en-TT|
|uk|GBR|en-GB|
|united-kingdom|GBR|en-GB|
|united-states|USA|en-US|
|us|USA|en-US|

## <a name="see-also"></a>См. также

[Сведения о строках имени языкового стандарта, языка, а также страны или региона](../c-runtime-library/locale-names-languages-and-country-region-strings.md)<br/>
[Строки языка](../c-runtime-library/language-strings.md)<br/>
[setlocale, _wsetlocale](../c-runtime-library/reference/setlocale-wsetlocale.md)<br/>
[_create_locale, _wcreate_locale](../c-runtime-library/reference/create-locale-wcreate-locale.md)
