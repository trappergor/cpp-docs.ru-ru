---
title: Оператор ComPtr::operator -&gt; оператора | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- client/Microsoft::WRL::ComPtr::operator->
dev_langs:
- C++
helpviewer_keywords:
- operator-> operator
ms.assetid: 7b7faefd-d1e4-4f31-a77d-17a42e0d6b6a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 0ff18dee2b8d951ab9233e92478eb967e4a02eb9
ms.sourcegitcommit: 51f804005b8d921468775a0316de52ad39b77c3e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/02/2018
ms.locfileid: "39464302"
---
# <a name="comptroperator-gt-operator"></a>Оператор ComPtr::operator -&gt; оператор
Извлекает указатель на тип, заданный текущим параметром шаблона.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
WRL_NOTHROW Microsoft::WRL::Details::RemoveIUnknown<InterfaceType>* operator->() const;  
```  
  
## <a name="return-value"></a>Возвращаемое значение  
 Указатель на тип, заданный текущим именем типа шаблона.  
  
## <a name="remarks"></a>Примечания  
 Эта вспомогательная функция удаляет лишнюю нагрузку, вызванную использованием макроса STDMETHOD. Эта функция делает `IUnknown` типы **частного** вместо **виртуального**.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** client.h  
  
 **Пространство имен:** Microsoft::WRL  
  
## <a name="see-also"></a>См. также  
 [Класс ComPtr](../windows/comptr-class.md)