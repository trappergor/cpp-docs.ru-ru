---
title: Входные LIB-файлы
ms.date: 11/04/2016
f1_keywords:
- Lib
helpviewer_keywords:
- input files, LIB
ms.assetid: e1236f0d-cd90-446b-b900-f311f456085c
ms.openlocfilehash: fb0095bd9e8699fbc9a1a144833d12d2cf4a1f83
ms.sourcegitcommit: bff17488ac5538b8eaac57156a4d6f06b37d6b7f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2019
ms.locfileid: "57423096"
---
# <a name="lib-input-files"></a>Входные LIB-файлы

Входные файлы LIB ожидает зависят от режима, в котором он используется, как показано в следующей таблице.

|Режим|Входные данные|
|----------|-----------|
|По умолчанию (Создание или изменение библиотеки)|COFF-файлы объектов (OBJ), COFF библиотеки (LIB), 32-разрядные файлы объектов (OBJ) формат объекта модели (OMF)|
|Извлечение члена с/Extract|COFF библиотека (.lib)|
|Построение экспорта файл и импортировать библиотеки с помощью/DEF|Файл определения модуля (DEF), COFF-файлы объектов (OBJ), COFF библиотеки (LIB), 32-разрядных OMF объектных файлах (.obj)|

> [!NOTE]
>  OMF-библиотеки, созданные в 16-разрядной версии LIB не может использоваться в качестве входных данных для 32-разрядной версии LIB.

## <a name="see-also"></a>См. также

[Общие сведения о LIB](../../build/reference/overview-of-lib.md)
