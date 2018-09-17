---
title: Выходные LIB-файлы | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- Lib
dev_langs:
- C++
helpviewer_keywords:
- output files, LIB
ms.assetid: e73d2f9b-a42d-402b-b7e3-3a94bebb317e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 23665897266bab87c71b8b3889688113fe8aa99a
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/17/2018
ms.locfileid: "45720711"
---
# <a name="lib-output-files"></a>Выходные LIB-файлы

Выходные файлы, создаваемые LIB зависят от режима, в котором он используется, как показано в следующей таблице.

|Режим|Вывод|
|----------|------------|
|По умолчанию (Создание или изменение библиотеки)|COFF библиотека (.lib)|
|Извлечение члена с/Extract|Файл объектов (OBJ)|
|Построение экспорта файл и импортировать библиотеки с помощью/DEF|Импорт библиотеки (.lib) и файла экспорта (EXP)|

## <a name="see-also"></a>См. также

[Общие сведения о LIB](../../build/reference/overview-of-lib.md)