---
title: "Конструктор Module::module | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::Module::Module
dev_langs:
- C++
helpviewer_keywords:
- Module, constructor
ms.assetid: 5436fc74-61dc-41b6-81af-4f03177159aa
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 24e74bf30f932fa8029c64d27ce55dd2a75a99aa
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
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