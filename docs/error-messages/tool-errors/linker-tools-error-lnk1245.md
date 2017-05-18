---
title: "Ошибка средств компоновщика LNK1245 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- LNK1245
dev_langs:
- C++
helpviewer_keywords:
- LNK1245
ms.assetid: 179c8165-ffbb-44cd-9f24-5250f29577cc
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: 11b00a11f617f8ee5eb17e53510b6f97300298fa
ms.contentlocale: ru-ru
ms.lasthandoff: 02/24/2017

---
# <a name="linker-tools-error-lnk1245"></a>Ошибка средств компоновщика LNK1245
Недопустимый подсистемы подсистемы задан; / SUBSYSTEM должен быть WINDOWS, WINDOWSCE или КОНСОЛИ  
  
 [/ CLR](../../build/reference/clr-common-language-runtime-compilation.md) был использован для компилирования объекта и одно из следующих условий верно:  
  
-   Точка добавления настраиваемой записи была определена ([/Entry](../../build/reference/entry-entry-point-symbol.md)), таким образом, что компоновщик не может повлиять на подсистему.  
  
-   Значение было передано [/SUBSYSTEM](../../build/reference/subsystem-specify-subsystem.md) параметра компоновщика, который недопустим для/CLR объектов.  
  
 Для обоих случаев решением является указать допустимое значение параметру компоновщика/SUBSYSTEM.
