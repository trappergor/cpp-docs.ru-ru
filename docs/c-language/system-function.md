---
title: "Функция system | Документация Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- system function
ms.assetid: 0786ccdc-20cd-4d96-b3d8-3230507c3066
caps.latest.revision: 7
author: mikeblome
ms.author: mblome
manager: ghogen
ms.translationtype: Human Translation
ms.sourcegitcommit: d6eb43b2e77b11f4c85f6cf7e563fe743d2a7093
ms.openlocfilehash: b504aedc5ad11edf40d7b797529065757dfb58e6
ms.contentlocale: ru-ru
ms.lasthandoff: 05/18/2017

---
# <a name="system-function"></a>Функция system
**ANSI 4.10.4.5** Содержимое и режим выполнения строки функцией **system**  
  
 Функция **system** выполняет внутреннюю команду операционной системы или файл .EXE, .COM (.CMD в Windows NT) или .BAT прямо из программы на языке C, а не в режиме командной строки.  
  
 Функция system находит интерпретатор команд (обычно это CMD.EXE в Windows NT или COMMAND.COM в Windows). Затем функция system передает строку аргумента в интерпретатору команд.  
  
 Дополнительные сведения см. в описании [system, _wsystem](../c-runtime-library/reference/system-wsystem.md).  
  
## <a name="see-also"></a>См. также  
 [Функции библиотеки](../c-language/library-functions.md)
