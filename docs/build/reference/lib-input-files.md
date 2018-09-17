---
title: LIB входные файлы | Документация Майкрософт
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
- input files, LIB
ms.assetid: e1236f0d-cd90-446b-b900-f311f456085c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 952c3345234192e3798fea483d527cd3afec4bff
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/17/2018
ms.locfileid: "45702472"
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