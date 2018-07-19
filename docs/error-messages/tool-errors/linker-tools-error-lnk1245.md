---
title: Ошибка средств компоновщика LNK1245 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK1245
dev_langs:
- C++
helpviewer_keywords:
- LNK1245
ms.assetid: 179c8165-ffbb-44cd-9f24-5250f29577cc
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 47a1c2e5f7bf66946dcc5816d7a20fd485b59b45
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33299244"
---
# <a name="linker-tools-error-lnk1245"></a>Ошибка средств компоновщика LNK1245
Недопустимая подсистема подсистемы задан; / SUBSYSTEM должен быть WINDOWS, WINDOWSCE или CONSOLE  
  
 [/ CLR](../../build/reference/clr-common-language-runtime-compilation.md) был использован для компилирования объекта и одно из следующих условий верно:  
  
-   Точка добавления настраиваемой записи был определен ([/Entry](../../build/reference/entry-entry-point-symbol.md)), таким образом, что компоновщик не может повлиять на подсистему.  
  
-   Значение было передано [/SUBSYSTEM](../../build/reference/subsystem-specify-subsystem.md) параметра компоновщика, который недопустим для/CLR объектов.  
  
 Для обоих случаев решением является указать допустимое значение для параметра компоновщика/SUBSYSTEM.