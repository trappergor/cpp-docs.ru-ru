---
title: __outword | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- __outword
dev_langs:
- C++
helpviewer_keywords:
- __outword intrinsic
- out instruction
ms.assetid: 995f8834-0f50-4b4f-a7a2-af0e7c371cda
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d118c26e79a462723f87e76672b2d9b9c1a76cb2
ms.sourcegitcommit: a41c4d096afca1e9b619bbbce045b77135d32ae2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/14/2018
ms.locfileid: "42541088"
---
# <a name="outword"></a>Встроенная функция __outword
**Блок, относящийся только к системам Microsoft**  
  
 Создает `out` инструкция, которая отправляет слово `Data` номера порта ввода-вывода, определяемое `Port`.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
void __outword(   
   unsigned short Port,   
   unsigned short Data   
);  
```  
  
#### <a name="parameters"></a>Параметры  
 [in] `Port`  
 Порт для отправки данных.  
  
 [in] `Data`  
 Передаваемые данные.  
  
## <a name="requirements"></a>Требования  
  
|Встроенная функция|Архитектура|  
|---------------|------------------|  
|`__outword`|x86, x64|  
  
 **Файл заголовка** \<intrin.h >  
  
## <a name="remarks"></a>Примечания  
 Эта процедура доступна только как встроенная функция.  
  
**Завершение блока, относящегося только к системам Майкрософт**  
  
## <a name="see-also"></a>См. также  
 [Встроенные инструкции компилятора](../intrinsics/compiler-intrinsics.md)