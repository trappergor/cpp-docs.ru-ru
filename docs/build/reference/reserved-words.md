---
title: Зарезервированные слова
ms.date: 11/04/2016
f1_keywords:
- code
- CONFORMING
- DISCARDABLE
- Description
- base
- APPLOADER
- Data
- DYNAMIC
- DEV386
helpviewer_keywords:
- .def files [C++], reserved words
- def files [C++], reserved words
- linker [C++], reserved words
- reserved words [C++]
ms.assetid: 9b9f49e5-0739-45ab-a37e-81e3915ceb25
ms.openlocfilehash: 7d51f599dfb81dfa860e1bdba86c4372e80379fb
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62319425"
---
# <a name="reserved-words"></a>Зарезервированные слова

Следующие слова зарезервированы компоновщиком. Эти имена можно использовать в качестве аргументов в [операторов определения модуля](module-definition-dot-def-files.md) только в том случае, если имя заключено в двойные кавычки (»»).

||||
|-|-|-|
|**APPLOADER**<sup>1</sup>|**INITINSTANCE**<sup>2</sup>|**ПРЕДВАРИТЕЛЬНАЯ ЗАГРУЗКА**|
|**BASE**|**IOPL**|**ЗАКРЫТЫЙ**|
|**КОД**|**БИБЛИОТЕКА**<sup>1</sup>|**PROTMODE**<sup>2</sup>|
|**УДОВЛЕТВОРЯЮЩИЕ**|**LOADONCALL**<sup>1</sup>|**ЧИСТЫЕ**<sup>1</sup>|
|**ДАННЫЕ**|**LONGNAMES**<sup>2</sup>|**ТОЛЬКО ДЛЯ ЧТЕНИЯ**|
|**ОПИСАНИЕ**|**ПЕРЕМЕЩАЕМЫЙ**<sup>1</sup>|**READWRITE**|
|**DEV386**|**MOVEABLE**<sup>1</sup>|**REALMODE**<sup>1</sup>|
|**ПРИСВАИВАЮТСЯ ЗНАЧЕНИЯ**|**НЕСКОЛЬКО**|**РЕЗИДЕНТНЫХ**|
|**ДИНАМИЧЕСКИЕ**|**ИМЯ**|**RESIDENTNAME**<sup>1</sup>|
|**ТОЛЬКО ДЛЯ ВЫПОЛНЕНИЯ**|**NEWFILES**<sup>2</sup>|**РАЗДЕЛЫ**|
|**EXECUTEONLY**|**NODATA**<sup>1</sup>|**СЕГМЕНТЫ**|
|**EXECUTEREAD**|**NOIOPL**<sup>1</sup>|**ОБЩИЕ**|
|**EXETYPE**|**NONAME**|**ЕДИНЫЙ**|
|**EXPORTS**|**НЕСООТВЕТСТВУЮЩИЕ**<sup>1</sup>|**STACKSIZE**|
|**ФИКСИРОВАННЫЙ**<sup>1</sup>|**NONDISCARDABLE**|**STUB**|
|**ФУНКЦИИ**<sup>2</sup>|**НЕТ**|**ВЕРСИЯ**|
|**HEAPSIZE**|**СОВМЕСТНО**|**WINDOWAPI**|
|**ИМПОРТЫ**|**NOTWINDOWCOMPAT**<sup>1</sup>|**WINDOWCOMPAT**|
|**ПОБОЧНЫМ ЭФФЕКТОМ**<sup>1</sup>|**ОБЪЕКТЫ**|**WINDOWS**|
|**ВКЛЮЧИТЬ**<sup>2</sup>|**СТАРЫЙ**<sup>1</sup>||

<sup>1</sup> Компоновщик выдает предупреждение («игнорировать»), когда он встречает этот термин. Тем не менее слово остается зарезервированным.

<sup>2</sup> компоновщик не обрабатывает это слово, но не выдает предупреждение.

## <a name="see-also"></a>См. также

- [Справочник по компоновщику MSVC](linking.md)
- [Параметры компоновщика MSVC](linker-options.md)