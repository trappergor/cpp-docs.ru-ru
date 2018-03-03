---
title: "Ошибка компилятора C2857 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2857
dev_langs:
- C++
helpviewer_keywords:
- C2857
ms.assetid: b57302bd-58ec-45ae-992a-1e282d5eeccc
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: c4bf637f0abb5affdb21deb8e081c8b5156afd88
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2857"></a>Ошибка компилятора C2857
"#include" инструкция, указанная с Ycfilename командной строки не найден в исходном файле  
  
 [/Yc](../../build/reference/yc-create-precompiled-header-file.md) параметр задает имя включаемого файла, который не включен в исходный файл, при компиляции.  
  
 Эта ошибка может быть вызвана `#include` оператор в блоке условной компиляции, который не компилируется.