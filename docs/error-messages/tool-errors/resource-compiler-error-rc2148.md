---
title: Ошибка компилятора ресурсов RC2148 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- RC2148
dev_langs:
- C++
helpviewer_keywords:
- RC2148
ms.assetid: 0290065c-35d3-4815-80c5-40bf7132ae1d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d10e18eef4691c0a018feb583ffb93499e86ccb6
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33320210"
---
# <a name="resource-compiler-error-rc2148"></a>Ошибка компилятора ресурсов RC2148
ДИАЛЕКТЕ ID слишком велик  
  
 Значение идентификатора варианта языка находится за пределами допустимого диапазона.  
  
 Оператор **LANGUAGE** должен использовать следующий синтаксис:  
  
 **LANGUAGE** *ИД_основного_языка*,*ИД_дополнительного_языка*  
  
 Допустимые идентификаторы ДИАЛЕКТЕ определяются как **SUBLANG_** константы в файле WINNT.h.