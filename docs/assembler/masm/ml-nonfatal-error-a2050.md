---
title: Некритичная ошибка ML A2050 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-masm
ms.topic: error-reference
f1_keywords:
- A2050
dev_langs:
- C++
helpviewer_keywords:
- A2050
ms.assetid: 16f3a58f-4bde-48f1-b0e3-2ed9612780a5
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 159ed131c13166435114234b3b16a82cd4d41d1f
ms.sourcegitcommit: dbca5fdd47249727df7dca77de5b20da57d0f544
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/28/2018
---
# <a name="ml-nonfatal-error-a2050"></a>Некритичная ошибка ML A2050
**реальный или BCD номер не разрешен**  
  
 Число с плавающей запятой (real) или константа двоично-десятичный (BCD) не использовался как инициализатор данных.  
  
 Произошло одно из следующих:  
  
-   Вещественное число или данных конфигурации загрузки был использован в выражении.  
  
-   Вещественное число был использован для инициализации директивы, отличный от [DWORD](../../assembler/masm/dword.md), [QWORD](../../assembler/masm/qword.md), или [TBYTE](../../assembler/masm/tbyte.md).  
  
-   BCD был использован для инициализации директивы, отличный от `TBYTE`.  
  
## <a name="see-also"></a>См. также  
 [Сообщения об ошибках ML](../../assembler/masm/ml-error-messages.md)