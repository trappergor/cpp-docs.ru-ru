---
title: "_WriteBarrier | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: _WriteBarrier
dev_langs: C++
helpviewer_keywords:
- WriteBarrier intrinsic
- _WriteBarrier intrinsic
ms.assetid: a5ffdad9-0ca1-4eb7-b2f3-0f092c4bf4b5
caps.latest.revision: "23"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: e619341e05d868b97d67fef068999c16fb2b4e60
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="writebarrier"></a>_WriteBarrier
**Блок, относящийся только к системам Microsoft**  
  
 Ограничивает оптимизации компилятора, которые могут изменить порядок операций доступа к памяти для точки вызова.  
  
> [!CAUTION]
>  Встроенные функции компилятора `_ReadBarrier`, `_WriteBarrier` и `_ReadWriteBarrier`, а также макрос `MemoryBarrier` являются нерекомендуемыми, и использовать их не следует. Для взаимодействия между потоками, использовать механизмы, такие как [atomic_thread_fence](../standard-library/atomic-functions.md#atomic_thread_fence) и [std::atomic\<T >](../standard-library/atomic.md), которые определены в [стандартной библиотеки C++](../standard-library/cpp-standard-library-reference.md). Доступ к оборудованию, используйте [/volatile:iso](../build/reference/volatile-volatile-keyword-interpretation.md) параметр компилятора вместе с [volatile](../cpp/volatile-cpp.md) ключевое слово.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
void _WriteBarrier(void);  
```  
  
## <a name="requirements"></a>Требования  
  
|Встроенная функция|Архитектура|  
|---------------|------------------|  
|`_WriteBarrier`|x86, [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
  
 **Файл заголовка** \<intrin.h >  
  
## <a name="remarks"></a>Примечания  
 Встроенная функция `_WriteBarrier` ограничивает оптимизации компилятора, которые могут удалять или изменять порядок операций доступа к памяти для точки вызова.  
  
**Завершение блока, относящегося только к системам Майкрософт**  
  
## <a name="see-also"></a>См. также  
 [_ReadBarrier](../intrinsics/readbarrier.md)   
 [_ReadWriteBarrier](../intrinsics/readwritebarrier.md)   
 [Встроенные объекты компилятора](../intrinsics/compiler-intrinsics.md)   
 [Ключевые слова](../cpp/keywords-cpp.md)