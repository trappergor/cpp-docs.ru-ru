---
title: "Предупреждение (уровень 1) C4799 компилятора | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4799
dev_langs:
- C++
helpviewer_keywords:
- C4799
ms.assetid: 8ecbd06f-c778-4371-a2fb-c690b6743ec8
caps.latest.revision: 7
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
ms.openlocfilehash: 617a6b2d009744adb0a53685976ee07266cf4490
ms.contentlocale: ru-ru
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-warning-level-1-c4799"></a>Предупреждение компилятора (уровень 1) C4799
Отсутствует инструкция EMMS в конце функции «функция»  
  
 Функция имеет по крайней мере одна инструкция MMX, но не поддерживает инструкцию EMMS. При использовании мультимедийной инструкции инструкцию EMMS также следует использовать для очистки word мультимедийного тега в конце кода MMX. Дополнительные сведения об инструкциях EMMS см. в разделе [рекомендации, когда для использования EMMS](http://msdn.microsoft.com/en-us/a0c3b1e4-01a4-419c-a58f-ff1e97dea7d3).  
  
 Может возникать предупреждение C4799, когда с помощью файла, указывающее на то, что код не использует правильно выполнять инструкции EMMS перед возвратом. Это предупреждение является ложным эти заголовки. Они могут отключить путем определения _SILENCE_IVEC_C4799 файла. Однако следует помнить, что это будет также запретить компилятору верные предупреждения этого типа.  
  
 Дополнительные сведения см. в разделе [набор инструкций MMX Intel](../../assembler/inline/intel-s-mmx-instruction-set.md).
