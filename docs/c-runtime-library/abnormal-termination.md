---
title: _abnormal_termination | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: conceptual
apiname:
- _abnormal_termination
apilocation:
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr90.dll
- msvcr120.dll
- msvcrt.dll
- msvcr80.dll
- msvcr100.dll
apitype: DLLExport
f1_keywords:
- _abnormal_termination
dev_langs:
- C++
helpviewer_keywords:
- _abnormal_termination
ms.assetid: 952970a4-9586-4c3d-807a-db729448c91c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f70520b60ccfaf1af5b223bcb4ea1a90639aa484
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="abnormaltermination"></a>_abnormal_termination
Указывает, выполнен ли вход в блок `__finally`[оператора try-finally](../cpp/try-finally-statement.md), когда система выполняет внутренний список обработчиков завершения.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
int   _abnormal_termination(  
   );  
```  
  
## <a name="return-value"></a>Возвращаемое значение  
 Значение `true`, если система *очищает* стек; в противном случае — значение `false`.  
  
## <a name="remarks"></a>Примечания  
 Это внутренняя функция, используемая для управления исключениями очистки, и она не должна вызываться из пользовательского кода.  
  
## <a name="requirements"></a>Требования  
  
|Подпрограмма|Обязательный заголовок|  
|-------------|---------------------|  
|_abnormal_termination|excpt.h|  
  
## <a name="see-also"></a>См. также  
 [Оператор try-finally](../cpp/try-finally-statement.md)