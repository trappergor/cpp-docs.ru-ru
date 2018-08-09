---
title: Метод Module::UnregisterCOMObject | Документация Майкрософт
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
ms.openlocfilehash: 240ab47099b9e97e9a6bb794083858fe042605d2
ms.sourcegitcommit: 38af5a1bf35249f0a51e3aafc6e4077859c8f0d9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/09/2018
ms.locfileid: "40018699"
---
# <a name="moduleunregistercomobject-method"></a>Метод Module::UnregisterCOMObject
Отменяет регистрацию одного или нескольких объектов модели COM, что предотвращает подключение к ним других приложений.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
virtual HRESULT UnregisterCOMObject(  
   const wchar_t* serverName,  
   DWORD* cookies,  
   unsigned int count  
```  
  
### <a name="parameters"></a>Параметры  
 *Имя_сервера*  
 (Не используется)  
  
 *Файлы cookie*  
 Массив указателей на значения, которые идентифицируют объекты класса для отмены регистрации. Массив был создан с [RegisterCOMObject](../windows/module-registercomobject-method.md) метод.  
  
 *count*  
 Количество классов для отмены регистрации.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Значение S_OK, если операция завершилась успешно; в противном случае — значение HRESULT, указывающее причину неудачного завершения операции.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** module.h  
  
 **Пространство имен:** Microsoft::WRL
 
 ## <a name="see-also"></a>См. также
 [Класс Module](../windows/module-class.md)