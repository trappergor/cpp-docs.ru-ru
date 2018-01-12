---
title: "MMWORD | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: MMWORD
dev_langs: C++
helpviewer_keywords: MMWORD directive
ms.assetid: b4c5a104-9078-4fb4-afc3-d1e63abe562a
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: bbe20f842a97186071431cd73e7de65fa8170bd4
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="mmword"></a>MMWORD
Используется для мультимедиа операндов 64-разрядных инструкций MMX и SSE (XMM).  
  
## <a name="syntax"></a>Синтаксис  
  
```  
MMWORD  
```  
  
## <a name="remarks"></a>Примечания  
 `MMWORD`— Это тип.  Перед добавлением MASM MMWORD можно достичь эквивалентную функциональность с:  
  
```  
mov mm0, qword ptr [ebx]  
```  
  
 Хотя обе инструкции работают на 64-разрядных операндов, `QWORD` является типом для 64-разрядных целых чисел без знака и `MMWORD` является типом для 64-разрядное значение мультимедиа.  
  
 `MMWORD`представляет тот же тип, что [__m64](../../cpp/m64.md).  
  
## <a name="example"></a>Пример  
  
```  
movq     mm0, mmword ptr [ebx]  
```