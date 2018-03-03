---
title: "Метод Module::UnregisterCOMObject | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::Module::UnregisterCOMObject
dev_langs:
- C++
helpviewer_keywords:
- UnregisterCOMObject method
ms.assetid: 5d377525-0385-482a-a215-6e8a1f032861
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 45a6dc776feb1534cd7e58240a40cc173e7459de
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
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