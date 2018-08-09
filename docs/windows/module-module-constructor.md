---
title: Конструктор Module::module | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::Module::Module
dev_langs:
- C++
helpviewer_keywords:
- Module, constructor
ms.assetid: 5436fc74-61dc-41b6-81af-4f03177159aa
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: d63b90bb3622129589fca41c029f548a07ec21b8
ms.sourcegitcommit: 38af5a1bf35249f0a51e3aafc6e4077859c8f0d9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/09/2018
ms.locfileid: "40017660"
---
# <a name="modulemodule-constructor"></a>Конструктор Module::Module
Инициализирует новый экземпляр класса **модуль** класса.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
Module();  
```  
  
## <a name="remarks"></a>Примечания  
 Этот конструктор является защищенным и не может вызываться с **новый** ключевое слово. Вместо этого вызовите [метод Module::GetModule](../windows/module-getmodule-method.md) или [метод Module::Create](../windows/module-create-method.md).  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** module.h  
  
 **Пространство имен:** Microsoft::WRL
 
 ## <a name="see-also"></a>См. также
 [Класс Module](../windows/module-class.md)