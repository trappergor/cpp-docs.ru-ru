---
title: no_dual_interfaces | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- no_dual_interfaces
dev_langs:
- C++
helpviewer_keywords:
- no_dual_interfaces attribute
ms.assetid: 9acd5d9d-4a49-4cdc-9470-73a2c23cf512
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 4eb26790a46f46638e4a4180ee2209efefda201c
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46432221"
---
# <a name="nodualinterfaces"></a>no_dual_interfaces
**Конкретных C++**  
  
Изменяет способ, которым компилятор создает функции оболочки для методов сдвоенных интерфейсов.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
no_dual_interfaces  
```  
  
## <a name="remarks"></a>Примечания  
 
Как правило, программа-оболочка вызывает метод через таблицу виртуальных функций интерфейса. С помощью **no_dual_interfaces**, вместо этого вызывает оболочки `IDispatch::Invoke` для вызова метода.  
  
**КОНЕЦ конкретных C++**  
  
## <a name="see-also"></a>См. также  
 
[атрибуты #import](../preprocessor/hash-import-attributes-cpp.md)<br/>
[директива #import](../preprocessor/hash-import-directive-cpp.md)