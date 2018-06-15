---
title: Зарезервированные слова | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- .def files [C++], reserved words
- def files [C++], reserved words
- linker [C++], reserved words
- reserved words [C++]
ms.assetid: 9b9f49e5-0739-45ab-a37e-81e3915ceb25
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 132bd8e5ba66cbf9486a6da4747994c667e2f6e7
ms.sourcegitcommit: a4454b91d556a3dc43d8755cdcdeabcc9285a20e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2018
ms.locfileid: "34705664"
---
# <a name="reserved-words"></a>Зарезервированные слова

Следующие слова зарезервированы компоновщиком. Эти имена могут использоваться как аргументы [операторов определения модуля](../../build/reference/module-definition-dot-def-files.md) только в том случае, если имя заключено в двойные кавычки (»»).

||||
|-|-|-|
|**APPLOADER**<sup>1</sup>|**INITINSTANCE**<sup>2</sup>|**ПРЕДВАРИТЕЛЬНАЯ ЗАГРУЗКА**|
|**BASE**|**IOPL**|**ЗАКРЫТЫЙ**|
|**КОД**|**БИБЛИОТЕКА**<sup>1</sup>|**PROTMODE**<sup>2</sup>|
|**СООТВЕТСТВУЮЩИЙ**|**LOADONCALL**<sup>1</sup>|**ЧИСТО**<sup>1</sup>|
|**ДАННЫЕ**|**LONGNAMES**<sup>2</sup>|**ТОЛЬКО ДЛЯ ЧТЕНИЯ**|
|**ОПИСАНИЕ**|**ПЕРЕМЕЩАЕМЫЙ**<sup>1</sup>|**READWRITE**|
|**DEV386**|**MOVEABLE**<sup>1</sup>|**REALMODE**<sup>1</sup>|
|**УДАЛЯЕМОЕ**|**НЕСКОЛЬКО**|**ВСТРОЕННЫЕ**|
|**ДИНАМИЧЕСКИЕ**|**ИМЯ**|**RESIDENTNAME**<sup>1</sup>|
|**ТОЛЬКО ДЛЯ ВЫПОЛНЕНИЯ**|**NEWFILES**<sup>2</sup>|**РАЗДЕЛЫ**|
|**EXECUTEONLY**|**NODATA**<sup>1</sup>|**СЕГМЕНТЫ**|
|**EXECUTEREAD**|**NOIOPL**<sup>1</sup>|**ОБЩИЕ**|
|**EXETYPE**|**NONAME**|**ОДИН**|
|**EXPORTS**|**НЕСООТВЕТСТВУЮЩИЕ**<sup>1</sup>|**STACKSIZE**|
|**ФИКСИРОВАННЫЙ**<sup>1</sup>|**NONDISCARDABLE**|**STUB**|
|**ФУНКЦИИ**<sup>2</sup>|**НЕТ**|**ВЕРСИЯ**|
|**HEAPSIZE**|**НЕ ОБЩИЕ**|**WINDOWAPI**|
|**ИМПОРТЫ**|**NOTWINDOWCOMPAT**<sup>1</sup>|**WINDOWCOMPAT**|
|**НЕЧИСТЫХ**<sup>1</sup>|**ОБЪЕКТЫ**|**WINDOWS**|
|**ВКЛЮЧИТЬ**<sup>2</sup>|**СТАРЫЙ**<sup>1</sup>||

<sup>1</sup> Компоновщик выдает предупреждение («используется»), когда он встречает этот термин. Тем не менее слово по-прежнему остается зарезервированным.

<sup>2</sup> компоновщик не обрабатывает это слово, но не выдает предупреждение.

## <a name="see-also"></a>См. также

- [Настройка параметров компоновщика](../../build/reference/setting-linker-options.md)
- [Параметры компоновщика](../../build/reference/linker-options.md)