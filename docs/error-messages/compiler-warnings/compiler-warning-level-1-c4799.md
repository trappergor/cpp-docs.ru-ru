---
title: Предупреждение (уровень 1) C4799 компилятора | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4799
dev_langs:
- C++
helpviewer_keywords:
- C4799
ms.assetid: 8ecbd06f-c778-4371-a2fb-c690b6743ec8
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f888d6a941ad487ce122e46c43582e1c96525c70
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33282942"
---
# <a name="compiler-warning-level-1-c4799"></a>Предупреждение компилятора (уровень 1) C4799  
  
> Отсутствует инструкция EMMS в конце функции "*функция*"  
  
Функция имеет по крайней мере один инструкций MMX, но не имеет `EMMS` инструкции. При использовании мультимедийной инструкции `EMMS` инструкции или `_mm_empty` встроенная функция также следует использовать для очистки мультимедийного тега слова в конце кода MMX.  
  
C4799 может возникнуть, когда с помощью файла, указывая, что код не правильно использовать выполнять инструкции EMMS перед возвратом. Это значение false, предупреждения для этих заголовков. Можно отключить эти определив _SILENCE_IVEC_C4799 файла. Однако имейте в виду, что это будет также запретить компилятору верные предупреждения этого типа.  
  
Дополнительные сведения см. в разделе [набор инструкций MMX Intel](../../assembler/inline/intel-s-mmx-instruction-set.md).