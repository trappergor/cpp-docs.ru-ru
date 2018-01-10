---
title: "XMMWORD | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: XMMWORD
dev_langs: C++
helpviewer_keywords: XMMWORD directive
ms.assetid: 18026d32-5cab-403e-ad7e-382fb41aa9b8
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: fa415124a11b307272305c87eabec35fafc13141
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="xmmword"></a>XMMWORD
Используется для 128-разрядный мультимедиа операндов с помощью инструкции MMX и SSE (XMM).  
  
## <a name="syntax"></a>Синтаксис  
  
```  
XMMWORD  
```  
  
## <a name="remarks"></a>Примечания  
 `XMMWORD`представляет тот же тип, что [__m128](../../cpp/m128.md).  
  
## <a name="example"></a>Пример  
  
```  
movdqa   xmm0, xmmword ptr [ebx]  
```