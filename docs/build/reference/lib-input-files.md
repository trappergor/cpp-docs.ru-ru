---
title: Входные LIB-файлы
ms.date: 11/04/2016
f1_keywords:
- Lib
helpviewer_keywords:
- input files, LIB
ms.assetid: e1236f0d-cd90-446b-b900-f311f456085c
ms.openlocfilehash: 885d03e74c7acff54e527c2dbad38de055913b5f
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50503335"
---
# <a name="lib-input-files"></a>Входные LIB-файлы

Входные файлы LIB ожидает зависят от режима, в котором он используется, как показано в следующей таблице.

|Режим|Ввод|
|----------|-----------|
|По умолчанию (Создание или изменение библиотеки)|COFF-файлы объектов (OBJ), COFF библиотеки (LIB), 32-разрядные файлы объектов (OBJ) формат объекта модели (OMF)|
|Извлечение члена с/Extract|COFF библиотека (.lib)|
|Построение экспорта файл и импортировать библиотеки с помощью/DEF|Файл определения модуля (DEF), COFF-файлы объектов (OBJ), COFF библиотеки (LIB), 32-разрядных OMF объектных файлах (.obj)|

> [!NOTE]
>  OMF-библиотеки, созданные в 16-разрядной версии LIB не может использоваться в качестве входных данных для 32-разрядной версии LIB.

## <a name="see-also"></a>См. также

[Общие сведения о LIB](../../build/reference/overview-of-lib.md)