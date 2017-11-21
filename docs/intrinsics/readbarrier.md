---
title: "_ReadBarrier | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: _ReadBarrier
dev_langs: C++
helpviewer_keywords: _ReadBarrier intrinsic
ms.assetid: f9e54a92-61bc-4f55-8195-b8932065a796
caps.latest.revision: "25"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 654d68ddf16dd0e162e0e50bbfb85f15fe9b5a86
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="readbarrier"></a>_ReadBarrier  
  
**Блок, относящийся только к системам Майкрософт**  
  
 Ограничивает оптимизации компилятора, которые могут изменить порядок операций доступа к памяти для точки вызова.  
  
> [!CAUTION]
>  Встроенные функции компилятора `_ReadBarrier`, `_WriteBarrier` и `_ReadWriteBarrier`, а также макрос `MemoryBarrier` являются нерекомендуемыми, и использовать их не следует. Для взаимодействия между потоками, использовать механизмы, такие как [atomic_thread_fence](../standard-library/atomic-functions.md#atomic_thread_fence) и [std::atomic\<T >](../standard-library/atomic.md) , определенные в [стандартной библиотеки C++](../standard-library/cpp-standard-library-reference.md). Доступ к оборудованию, используйте [/volatile:iso](../build/reference/volatile-volatile-keyword-interpretation.md) параметр компилятора вместе с [volatile](../cpp/volatile-cpp.md) ключевое слово.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
void _ReadBarrier(void);  
```  
  
## <a name="requirements"></a>Требования  
  
|Встроенная функция|Архитектура|  
|---------------|------------------|  
|`_ReadBarrier`|x86, [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
  
 **Файл заголовка** \<intrin.h >  
  
## <a name="remarks"></a>Примечания  
 Встроенная функция `_ReadBarrier` ограничивает оптимизации компилятора, которые могут удалять или изменять порядок операций доступа к памяти для точки вызова.  
  
**Завершение блока, относящегося только к системам Майкрософт**  
  
## <a name="see-also"></a>См. также  
 [Встроенные объекты компилятора](../intrinsics/compiler-intrinsics.md)   
 [Ключевые слова](../cpp/keywords-cpp.md)