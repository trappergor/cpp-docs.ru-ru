---
title: "Метод Module::GetClassObject | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::Module::GetClassObject
dev_langs:
- C++
helpviewer_keywords:
- GetClassObject method
ms.assetid: 95b0de1b-f728-4f96-9f44-f6ea71ce56e4
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 3f234b46da1a70ee0256a9a38ebb2ef7ae0bb5bb
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
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