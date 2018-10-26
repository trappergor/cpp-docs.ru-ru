---
title: Ошибка средств компоновщика LNK1106 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK1106
dev_langs:
- C++
helpviewer_keywords:
- LNK1106
ms.assetid: 528f7e65-04be-4966-b8af-9276837c7cda
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ce6a8b2ef9ac807e48cff42186453666cebda5ee
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/25/2018
ms.locfileid: "50055988"
---
# <a name="linker-tools-error-lnk1106"></a>Ошибка средств компоновщика LNK1106

Недопустимый файл или диск заполнен: не удается выполнить поиск в расположение

Средство не может считывать или записывать `location` в файл, размещенный в памяти.

### <a name="to-fix-by-checking-the-following-possible-causes"></a>Чтобы устранить ошибку, проверьте указанные ниже возможные причины ее возникновения.

1. Диск заполнен.

   Освободите место на диске и снова связать.

1. Попытка выполнить компоновку по сети.

   Некоторые сети не полностью поддерживают отображенного в память файлы, используемые компоновщиком. Попробовать выполнить компоновку на локальном диске.

1. Поврежденный блок на диске.

   Несмотря на то, что операционная система и оборудование диска должна была обнаруживать, такая ошибка, можно запустить программу проверки диска.

1. Хватает размера кучи.

   См. в разделе [C1060](../../error-messages/compiler-errors-1/fatal-error-c1060.md) Дополнительные сведения.