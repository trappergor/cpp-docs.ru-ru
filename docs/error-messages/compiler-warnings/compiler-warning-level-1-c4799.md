---
title: "Предупреждение (уровень 1) C4799 компилятора | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4799
dev_langs: C++
helpviewer_keywords: C4799
ms.assetid: 8ecbd06f-c778-4371-a2fb-c690b6743ec8
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 9f41535c01d67e28baa2569ace2684865407a1d1
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-1-c4799"></a>Предупреждение компилятора (уровень 1) C4799  
  
> Отсутствует инструкция EMMS в конце функции "*функция*"  
  
Функция имеет по крайней мере один инструкций MMX, но не имеет `EMMS` инструкции. При использовании мультимедийной инструкции `EMMS` инструкции или `_mm_empty` встроенная функция также следует использовать для очистки мультимедийного тега слова в конце кода MMX.  
  
C4799 может возникнуть, когда с помощью файла, указывая, что код не правильно использовать выполнять инструкции EMMS перед возвратом. Это значение false, предупреждения для этих заголовков. Можно отключить эти определив _SILENCE_IVEC_C4799 файла. Однако имейте в виду, что это будет также запретить компилятору верные предупреждения этого типа.  
  
Дополнительные сведения см. в разделе [набор инструкций MMX Intel](../../assembler/inline/intel-s-mmx-instruction-set.md).