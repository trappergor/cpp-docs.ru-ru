---
title: ". FPO | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: .FPO
dev_langs: C++
helpviewer_keywords: .FPO directive
ms.assetid: 35f4cd61-32f9-4262-b657-73f04f775d09
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: fc26358e1da11ada6b23364576bfedb379bc4030
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="fpo"></a>.FPO
. Директива FPO управляет вывод записи об отладке F сегмент .debug$ или раздел.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
FPO (  
cdwLocals  
,   
cdwParams  
,   
cbProlog  
,   
cbRegs  
,   
fUseBP  
,   
cbFrame  
)  
  
```  
  
#### <a name="parameters"></a>Параметры  
 `cdwLocals`  
 Количество локальных переменных, значение без знака 32-разрядная версия.  
  
 `cdwParams`  
 Размер параметров в тех 16 битовое значение без знака.  
  
 *cbProlog*  
 Число байтов кода пролога функции 8 битовое значение без знака.  
  
 `cbRegs`  
 Номер регистры, сохраненные.  
  
 `fUseBP`  
 Указывает, выделен ли регистр EBP. 0 или 1.  
  
 *cbFrame*  
 Указывает тип кадра.  В разделе [FPO_DATA](http://msdn.microsoft.com/library/windows/desktop/ms679352) для получения дополнительной информации.  
  
## <a name="see-also"></a>См. также  
 [Справочник по директивам](../../assembler/masm/directives-reference.md)