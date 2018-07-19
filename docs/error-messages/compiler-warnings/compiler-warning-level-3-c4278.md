---
title: Предупреждение (уровень 3) C4278 компилятора | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4278
dev_langs:
- C++
helpviewer_keywords:
- C4278
ms.assetid: 4b6053fb-df62-4c04-b6c8-c011759557b8
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7b556166f61c5d77ac34fb7243ac25d5baeaa2b1
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33296680"
---
# <a name="compiler-warning-level-3-c4278"></a>Предупреждение компилятора (уровень 3) C4278
«Идентификатор»: идентификатор в библиотеке типов «tlb» уже является макроопределением; Используйте квалификатор «rename»  
  
 При использовании [#import](../../preprocessor/hash-import-directive-cpp.md), идентификатор в импорте библиотеки типов пытается объявить идентификатор ***идентификатор***. Тем не менее уже допустимый символ.  
  
 Используйте `#import` **переименование** атрибут, чтобы назначить псевдоним для символа в библиотеке типов.