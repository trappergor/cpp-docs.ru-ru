---
title: Метод Module::RegisterWinRTObject | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::Module::RegisterWinRTObject
dev_langs:
- C++
helpviewer_keywords:
- RegisterWinRTObject method
ms.assetid: a2782c9c-b9c5-4e4b-9c8d-ef513aea20c5
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 42ec736126e2381b00542bf71afca0b9db187df7
ms.sourcegitcommit: 4586bfc32d8bc37ab08b24816d7fad5df709bfa3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/07/2018
ms.locfileid: "39603761"
---
# <a name="moduleregisterwinrtobject-method"></a>Метод Module::RegisterWinRTObject
Регистрирует один или несколько объектов среды выполнения Windows, чтобы другие приложения могли подключиться к ним.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT RegisterWinRTObject(const wchar_t* serverName,  
   wchar_t** activatableClassIds,  
   WINRT_REGISTRATION_COOKIE* cookie,  
   unsigned int count)  
```  
  
### <a name="parameters"></a>Параметры  
 *Имя_сервера*  
 Имя, которое определяет подмножество объектов, затронутых этой операцией.  
  
 *activatableClassIds*  
 Массив активируемых идентификаторов CLSID для регистрации.  
  
 *Файл cookie*  
 Значение, которое идентифицирует зарегистрированные объекты класса. Это значение в дальнейшем используется для отмены регистрации.  
  
 *count*  
 Количество объектов, которое необходимо зарегистрировать.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Значение S_OK, если операция завершилась успешно; в противном случае — значение HRESULT (например, CO_E_OBJISREG), указывающее причину неудачного завершения операции.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** module.h  
  
 **Пространство имен:** Microsoft::WRL
 
 ## <a name="see-also"></a>См. также
 [Класс Module](../windows/module-class.md)