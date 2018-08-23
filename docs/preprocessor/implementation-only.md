---
title: implementation_only | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- implementation_only
dev_langs:
- C++
helpviewer_keywords:
- implementation_only attribute
ms.assetid: d8cabc86-4425-45a0-9587-d57536980088
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 2e7f0f40ad5d01b647f1f3273dc9a55d7cfa7564
ms.sourcegitcommit: d4c803bd3a684d7951bf88dcecf1f14af43ae411
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/10/2018
ms.locfileid: "42541838"
---
# <a name="implementationonly"></a>implementation_only
**Конкретных C++**  
  
Отключает создание файла заголовка .tlh (основного файла заголовка).  
  
## <a name="syntax"></a>Синтаксис  
  
```  
implementation_only  
```  
  
## <a name="remarks"></a>Примечания  
 
Этот файл содержит все объявления, используемые для предоставления содержимого библиотек типов. Будет создан и включен в компиляцию файл заголовка .tli, содержащий реализации функций-членов оболочки.  
  
Если этот атрибут указан, содержимое заголовка .tli находится в том же пространстве имен, которое обычно используется в заголовке .tlh. Кроме того, функции-члены не объявляются как встроенные.  
  
**Implementation_only** атрибут предназначен для использования в сочетании с [no_implementation](../preprocessor/no-implementation.md) атрибут как способ хранение реализаций в файл предкомпилированного заголовка (PCH). Оператор `#import` с атрибутом `no_implementation` размещается в области исходного кода, использованной для создания файла PCH. Получающийся файл PCH используется несколькими файлами исходного кода. `#import` Инструкции с **implementation_only** атрибута используется вне области PCH. Этот оператор можно использовать только один раз в одном из файлов исходного кода. При этом будут созданы все необходимые функции-члены оболочки без дополнительной повторной компиляции каждого файла исходного кода.  
  
> [!NOTE]
> **Implementation_only** атрибут в одном `#import` инструкция должна быть использования в сочетании с другим `#import` инструкции одной и той же библиотеки типов с `no_implementation` атрибута. В противном случае возникнут ошибки компилятора. Это обусловлено тем, создаваемые определения класса-оболочки `#import` инструкции с `no_implementation` атрибута, должны компилировать реализации, создаваемые **implementation_only** атрибута.  
  
**КОНЕЦ конкретных C++**  
  
## <a name="see-also"></a>См. также  
 
[атрибуты #import](../preprocessor/hash-import-attributes-cpp.md)   
[директива #import](../preprocessor/hash-import-directive-cpp.md)