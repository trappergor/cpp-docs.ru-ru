---
title: "Предупреждение средств компоновщика LNK4102 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: LNK4102
dev_langs: C++
helpviewer_keywords: LNK4102
ms.assetid: bfd1b17e-05c7-4bc2-80d6-2888b1a425b2
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 80efad60da9f6742110811a5cf4c12f07c7def67
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="linker-tools-warning-lnk4102"></a>Предупреждение средств компоновщика LNK4102
Экспорт деструктора удаления «имя»; образ может неправильно выполняться  
  
 Программа попыталась экспортировать удаленный деструктор. Полученный delete может возникнуть через границу DLL таким образом, процесс может освободить память, которой не было. Убедитесь, что данный символ не присутствует в DEF-файле и не находится в аргумента **/ИМПОРТ** или **и экспорт** параметр в командной строке компоновщика.  
  
 Если выполняется перестроение библиотеки времени выполнения C, это сообщение можно проигнорировать.