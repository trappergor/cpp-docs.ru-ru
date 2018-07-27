---
title: Предупреждение средств компоновщика LNK4014 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK4014
dev_langs:
- C++
helpviewer_keywords:
- LNK4014
ms.assetid: 394903e9-3ded-4ea4-b7c0-a3535d4b4da4
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 2fb86efbdc70342861a87a233ab687f7564cb48b
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33300063"
---
# <a name="linker-tools-warning-lnk4014"></a>Предупреждение средств компоновщика LNK4014
не удается найти объект члена «objectname»  
  
 Не удалось найти LIB `objectname` в библиотеке.  
  
 **/Удаление** и **/EXTRACT** параметров требуется полное имя объекта-члена, удаляемого или скопировать в файл. Полное имя включает путь к исходному файлу объекта. Для просмотра полных имен объектов-членов в библиотеке, использование служебной программы DUMPBIN [/ARCHIVEMEMBERS](../../build/reference/archivemembers.md) или LIB [/LIST](../../build/reference/managing-a-library.md).