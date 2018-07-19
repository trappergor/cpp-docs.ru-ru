---
title: Предупреждение средств компоновщика LNK4102 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK4102
dev_langs:
- C++
helpviewer_keywords:
- LNK4102
ms.assetid: bfd1b17e-05c7-4bc2-80d6-2888b1a425b2
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 16d13dcbc6d15efd7cf3a7ea0a310de4ab7b0c93
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33302650"
---
# <a name="linker-tools-warning-lnk4102"></a>Предупреждение средств компоновщика LNK4102
Экспорт деструктора удаления «имя»; образ может неправильно выполняться  
  
 Программа попыталась экспортировать удаленный деструктор. Полученный delete может возникнуть через границу DLL таким образом, процесс может освободить память, которой не было. Убедитесь, что данный символ не присутствует в DEF-файле и не находится в аргумента **/ИМПОРТ** или **и экспорт** параметр в командной строке компоновщика.  
  
 Если выполняется перестроение библиотеки времени выполнения C, это сообщение можно проигнорировать.