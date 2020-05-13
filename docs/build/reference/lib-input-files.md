---
title: Входные LIB-файлы
ms.date: 11/04/2016
helpviewer_keywords:
- input files, LIB
ms.assetid: e1236f0d-cd90-446b-b900-f311f456085c
ms.openlocfilehash: de81f79eecf3fc73c02894747f4b97cb107cf892
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81328230"
---
# <a name="lib-input-files"></a>Входные LIB-файлы

Вхотовые файлы, ожидаемые LIB, зависят от режима, в котором он используется, как показано в следующей таблице.

|Режим|Входные данные|
|----------|-----------|
|По умолчанию (создание или изменение библиотеки)|COFF объект (.obj) файлы, библиотеки COFF (.lib), 32-битный объект Формат модели (OMF) объект (.obj) файлы|
|Извлечение участника с помощью /EXTRACT|Библиотека COFF (.lib)|
|Создание экспортного файла и библиотеки импорта с /DEF|Модуль-определение (.def) файл, COFF объект (.obj) файлы, библиотеки COFF (.lib), 32-разрядный объект OMF (.obj) файлы|

> [!NOTE]
> Библиотеки OMF, созданные 16-битной версией LIB, не могут использоваться в качестве ввода в 32-битную версию LIB.

## <a name="see-also"></a>См. также раздел

[Общие сведения о LIB](overview-of-lib.md)
