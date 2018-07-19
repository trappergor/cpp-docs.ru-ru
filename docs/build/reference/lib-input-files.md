---
title: Входные LIB файлы | Документы Microsoft
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
ms.openlocfilehash: 140a0f1d9ef6fdb3ca5e6d6977804684c88af1fb
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32371971"
---
# <a name="lib-input-files"></a>Входные LIB-файлы
Входные файлы LIB ожидает зависят от режима, в котором он используется, как показано в следующей таблице.  
  
|Режим|Ввод|  
|----------|-----------|  
|По умолчанию (Создание или изменение библиотеки)|COFF-файлы объектов (OBJ), COFF библиотеки (LIB), 32-разрядных формат объекта модели (OMF) объектных файлах (.obj)|  
|Извлечение члена с/Extract|COFF библиотеки (LIB)|  
|Построение Экспорт файла и библиотеки импорта с/DEF|Файл определения модуля (DEF), COFF объектных файлах (.obj), COFF библиотеки (LIB), 32-разрядных OMF объектных файлах (.obj)|  
  
> [!NOTE]
>  OMF-библиотеки, созданных 16-разрядную версию LIB не может использоваться как входные данные для 32-разрядной версии LIB.  
  
## <a name="see-also"></a>См. также  
 [Общие сведения о LIB](../../build/reference/overview-of-lib.md)