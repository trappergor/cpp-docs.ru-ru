---
title: "__writeeflags | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: __writeeflags
dev_langs: C++
helpviewer_keywords: __writeeflags intrinsics
ms.assetid: a62a522c-d7fa-4f10-a620-a3b32bdf3f17
caps.latest.revision: "5"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 1b87ffaacbbfee167c779f25ae83090b7b8e3397
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="writeeflags"></a>__writeeflags
Записывает указанное значение в программу регистрации состояния и управления (EFLAGS).  
  
## <a name="syntax"></a>Синтаксис  
  
```  
void __writeeflags(unsigned Value);  
void __writeeflags(unsigned __int64 Value);  
```  
  
#### <a name="parameters"></a>Параметры  
  
|Параметр|Описание|  
|---------------|-----------------|  
|[in] `Value`|Значение для записи в EFLAGS регистр. `Value` Параметр — 32 бита, для 32-разрядной платформе и 64-разрядная для 64-разрядной платформе.|  
  
## <a name="remarks"></a>Примечания  
 Эти процедуры доступны только как встроенные объекты.  
  
## <a name="requirements"></a>Требования  
  
|Встроенная функция|Архитектура|  
|---------------|------------------|  
|`__writeeflags`|x86, [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
  
 **Файл заголовка** \<intrin.h >  
  
**Завершение блока, относящегося только к системам Майкрософт**  
  
## <a name="see-also"></a>См. также  
 [Встроенные объекты компилятора](../intrinsics/compiler-intrinsics.md)   
 [__readeflags](../intrinsics/readeflags.md)