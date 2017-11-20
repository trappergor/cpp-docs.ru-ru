---
title: "Входные LIB файлы | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: Lib
dev_langs: C++
helpviewer_keywords: input files, LIB
ms.assetid: e1236f0d-cd90-446b-b900-f311f456085c
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: f956dedb8be270eb9974fa035d38e7fbb6714499
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="lib-input-files"></a>Входные LIB-файлы
Входные файлы LIB ожидает зависят от режима, в котором он используется, как показано в следующей таблице.  
  
|Mode|Ввод|  
|----------|-----------|  
|По умолчанию (Создание или изменение библиотеки)|COFF-файлы объектов (OBJ), COFF библиотеки (LIB), 32-разрядных формат объекта модели (OMF) объектных файлах (.obj)|  
|Извлечение члена с/Extract|COFF библиотеки (LIB)|  
|Построение Экспорт файла и библиотеки импорта с/DEF|Файл определения модуля (DEF), COFF объектных файлах (.obj), COFF библиотеки (LIB), 32-разрядных OMF объектных файлах (.obj)|  
  
> [!NOTE]
>  OMF-библиотеки, созданных 16-разрядную версию LIB не может использоваться как входные данные для 32-разрядной версии LIB.  
  
## <a name="see-also"></a>См. также  
 [Общие сведения о LIB](../../build/reference/overview-of-lib.md)