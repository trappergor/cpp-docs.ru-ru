---
title: . FPO | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-masm
ms.topic: reference
f1_keywords:
- .FPO
dev_langs:
- C++
helpviewer_keywords:
- .FPO directive
ms.assetid: 35f4cd61-32f9-4262-b657-73f04f775d09
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 234ec5bd703a390d1e2ee60e48d99d346d4aad95
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/29/2018
ms.locfileid: "43203117"
---
# <a name="fpo"></a>.FPO
. Директива FPO контролирует вывод записи об отладке .debug$ F сегмента или раздел.  
  
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
 Размер параметров в ЧЕТЫРЕХБАЙТОВЫЙ, значение без знака 16-разрядных систем.  
  
 *cbProlog*  
 Число байтов в кода пролога функции значение 8-разрядное число без знака.  
  
 `cbRegs`  
 Номер сохраненные регистры.  
  
 `fUseBP`  
 Указывает, выделен ли регистр EBP. 0 или 1.  
  
 *cbFrame*  
 Указывает тип пакета.  См. в разделе [FPO_DATA](/windows/desktop/api/winnt/ns-winnt-_fpo_data) Дополнительные сведения.  
  
## <a name="see-also"></a>См. также  
 [Справочник по директивам](../../assembler/masm/directives-reference.md)