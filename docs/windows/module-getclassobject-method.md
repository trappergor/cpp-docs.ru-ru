---
title: Метод Module::GetClassObject | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::Module::GetClassObject
dev_langs:
- C++
helpviewer_keywords:
- GetClassObject method
ms.assetid: 95b0de1b-f728-4f96-9f44-f6ea71ce56e4
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 9205b04fc27e1c6e0e6133a08c3c2f69ffdfc314
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2018
ms.locfileid: "33878542"
---
# <a name="modulegetclassobject-method"></a>Метод Module::GetClassObject
Извлекает кэш фабрик классов.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
 HRESULT GetClassObject(  
   REFCLSID clsid,  
   REFIID riid,  
   _Deref_out_ void **ppv,  
   wchar_t* serverName = nullptr  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `clsid`  
 Идентификатор класса.  
  
 `riid`  
 Запрошенный идентификатор интерфейса.  
  
 `ppv`  
 Указатель на возвращаемый объект.  
  
 `serverName`  
 Имя сервера, указанное в макросе `ActivatableClassWithFactory`, `ActivatableClassWithFactoryEx` или `ActivatableClass`; в противном случае — значение `nullptr` для получения имени сервера по умолчанию.  
  
## <a name="return-value"></a>Возвращаемое значение  
  
## <a name="remarks"></a>Примечания  
 Используйте этот метод только для модели COM, а не средой выполнения Windows. Этот метод реализует только методы IClassFactory.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** module.h  
  
 **Пространство имен:** Microsoft::WRL
 
 ## <a name="see-also"></a>См. также
 [Класс Module](../windows/module-class.md)