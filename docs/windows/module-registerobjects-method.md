---
title: Метод Module::RegisterObjects | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::Module::RegisterObjects
dev_langs:
- C++
helpviewer_keywords:
- RegisterObjects method
ms.assetid: db4077b7-068d-4534-aaa5-41b5444ccb49
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 04281b87584d10d36f5f2eeea05dfae0923b2d9f
ms.sourcegitcommit: 38af5a1bf35249f0a51e3aafc6e4077859c8f0d9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/09/2018
ms.locfileid: "40013318"
---
# <a name="moduleregisterobjects-method"></a>Метод Module::RegisterObjects
Регистрирует объекты COM или среду выполнения Windows, чтобы другие приложения могли подключиться к ним.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT RegisterObjects(  
   ModuleBase* module,   
   const wchar_t* serverName);  
```  
  
### <a name="parameters"></a>Параметры  
 *модуль*  
 Массив объектов COM или среду выполнения Windows.  
  
 *Имя_сервера*  
 Имя сервера, который создал объекты.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Значение S_OK, если операция завершилась успешно; в противном случае — значение HRESULT, указывающее причину неудачного завершения операции.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** module.h  
  
 **Пространство имен:** Microsoft::WRL
 
## <a name="see-also"></a>См. также
[Класс Module](../windows/module-class.md)