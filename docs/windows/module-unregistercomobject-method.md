---
title: Метод Module::UnregisterCOMObject | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::Module::UnregisterCOMObject
dev_langs:
- C++
helpviewer_keywords:
- UnregisterCOMObject method
ms.assetid: 5d377525-0385-482a-a215-6e8a1f032861
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: de4cc44d88f59e18f2c1644e9b27a9214ad32962
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2018
---
# <a name="moduleunregistercomobject-method"></a>Метод Module::UnregisterCOMObject
Отменяет регистрацию одного или нескольких объектов модели COM, что предотвращает подключение к ним других приложений.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
virtual HRESULT UnregisterCOMObject(  
   const wchar_t* serverName,  
   DWORD* cookies,  
   unsigned int count  
```  
  
#### <a name="parameters"></a>Параметры  
 `serverName`  
 (Не используется)  
  
 `cookies`  
 Массив указателей на значения, которые идентифицируют объекты класса для отмены регистрации. Массив был создан с помощью [RegisterCOMObject](../windows/module-registercomobject-method.md) метод.  
  
 `count`  
 Количество классов для отмены регистрации.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Значение S_OK, если операция завершилась успешно; в противном случае — значение HRESULT, указывающее причину неудачного завершения операции.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** module.h  
  
 **Пространство имен:** Microsoft::WRL
 
 ## <a name="see-also"></a>См. также
 [Класс Module](../windows/module-class.md)