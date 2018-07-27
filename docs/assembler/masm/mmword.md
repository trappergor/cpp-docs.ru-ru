---
title: MMWORD | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-masm
ms.topic: reference
f1_keywords:
- MMWORD
dev_langs:
- C++
helpviewer_keywords:
- MMWORD directive
ms.assetid: b4c5a104-9078-4fb4-afc3-d1e63abe562a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e97b1e58116d633519b1a780928e05862ac1771d
ms.sourcegitcommit: dbca5fdd47249727df7dca77de5b20da57d0f544
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/28/2018
ms.locfileid: "32054784"
---
# <a name="mmword"></a>MMWORD
Используется для мультимедиа операндов 64-разрядных инструкций MMX и SSE (XMM).  
  
## <a name="syntax"></a>Синтаксис  
  
```  
MMWORD  
```  
  
## <a name="remarks"></a>Примечания  
 `MMWORD` — Это тип.  Перед добавлением MASM MMWORD можно достичь эквивалентную функциональность с:  
  
```  
mov mm0, qword ptr [ebx]  
```  
  
 Хотя обе инструкции работают на 64-разрядных операндов, `QWORD` является типом для 64-разрядных целых чисел без знака и `MMWORD` является типом для 64-разрядное значение мультимедиа.  
  
 `MMWORD` представляет тот же тип, что [__m64](../../cpp/m64.md).  
  
## <a name="example"></a>Пример  
  
```  
movq     mm0, mmword ptr [ebx]  
```