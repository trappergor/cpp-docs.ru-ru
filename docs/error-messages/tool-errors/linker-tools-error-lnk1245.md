---
title: "Ошибка средств компоновщика LNK1245 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: LNK1245
dev_langs: C++
helpviewer_keywords: LNK1245
ms.assetid: 179c8165-ffbb-44cd-9f24-5250f29577cc
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 142d88489748f30308395d64f3db78178a9b856f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="linker-tools-error-lnk1245"></a>Ошибка средств компоновщика LNK1245
Недопустимая подсистема подсистемы задан; / SUBSYSTEM должен быть WINDOWS, WINDOWSCE или CONSOLE  
  
 [/ CLR](../../build/reference/clr-common-language-runtime-compilation.md) был использован для компилирования объекта и одно из следующих условий верно:  
  
-   Точка добавления настраиваемой записи был определен ([/Entry](../../build/reference/entry-entry-point-symbol.md)), таким образом, что компоновщик не может повлиять на подсистему.  
  
-   Значение было передано [/SUBSYSTEM](../../build/reference/subsystem-specify-subsystem.md) параметра компоновщика, который недопустим для/CLR объектов.  
  
 Для обоих случаев решением является указать допустимое значение для параметра компоновщика/SUBSYSTEM.