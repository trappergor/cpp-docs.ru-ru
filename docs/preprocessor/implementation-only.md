---
title: implementation_only | Документы Microsoft
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
ms.openlocfilehash: 0a3a2cbf0b39dc1c5f5462ae105e2206d70a38f4
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2018
ms.locfileid: "33912827"
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
  
 `implementation_only` Атрибут предназначен для использования в сочетании с [no_implementation](../preprocessor/no-implementation.md) атрибут как способ хранения реализаций из файла предкомпилированного заголовка (PCH). Оператор `#import` с атрибутом `no_implementation` размещается в области исходного кода, использованной для создания файла PCH. Получающийся файл PCH используется несколькими файлами исходного кода. Затем оператор `#import` с атрибутом `implementation_only` используется вне области PCH. Этот оператор можно использовать только один раз в одном из файлов исходного кода. При этом будут созданы все необходимые функции-члены оболочки без дополнительной повторной компиляции каждого файла исходного кода.  
  
> [!NOTE]
>  Атрибут `implementation_only` в одном операторе `#import` должен использоваться вместе с другим оператором `#import` для той же библиотеки типов с атрибутом `no_implementation`. В противном случае возникнут ошибки компилятора. Это происходит потому, что определения класса-оболочки, создаваемые оператором `#import` с атрибутом `no_implementation`, должны компилировать реализации, создаваемые атрибутом `implementation_only`.  
  
 **КОНЕЦ определенного C++**  
  
## <a name="see-also"></a>См. также  
 [атрибуты #import](../preprocessor/hash-import-attributes-cpp.md)   
 [директива #import](../preprocessor/hash-import-directive-cpp.md)