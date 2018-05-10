---
title: Конструктор Module::module | Документы Microsoft
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
ms.openlocfilehash: b31e9f1e4536bc124bba359ece10217ef8b7f253
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2018
---
# <a name="modulemodule-constructor"></a>Конструктор Module::Module
Инициализирует новый экземпляр класса Module.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
Module();  
```  
  
## <a name="remarks"></a>Примечания  
 Этот конструктор является защищенным и не может быть вызван ключевым словом `new`. Вместо этого необходимо вызвать либо [метод Module::GetModule](../windows/module-getmodule-method.md) или [метод Module::Create](../windows/module-create-method.md).  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** module.h  
  
 **Пространство имен:** Microsoft::WRL
 
 ## <a name="see-also"></a>См. также
 [Класс Module](../windows/module-class.md)