---
title: Метод WeakReference::Resolve | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::Details::WeakReference::Resolve
dev_langs:
- C++
helpviewer_keywords:
- Resolve method
ms.assetid: fc65a4b7-48a0-4d64-a793-37f566fdd8e7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 93df4ebf46b187cab63fbfaed2e273c55e7c0d84
ms.sourcegitcommit: 38af5a1bf35249f0a51e3aafc6e4077859c8f0d9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/09/2018
ms.locfileid: "40013253"
---
# <a name="weakreferenceresolve-method"></a>Метод WeakReference::Resolve
Поддерживает инфраструктуру WRL и не предназначен для использования непосредственно из программного кода.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
STDMETHOD(Resolve)  
   (REFIID riid,   
   _Deref_out_opt_ IInspectable **ppvObject  
);  
```  
  
### <a name="parameters"></a>Параметры  
 *riid*  
 Идентификатор интерфейса.  
  
 *ppvObject*  
 После завершения этой операции копию текущей строгую ссылку, если величина строгая ссылка имеет ненулевое значение.  
  
## <a name="return-value"></a>Возвращаемое значение  
  
-   Значение S_OK, если операция выполнена успешно и строгую ссылку счетчик равен нулю. *PpvObject* параметр имеет значение **nullptr**.  
  
-   Значение S_OK, если операция выполнена успешно и строгую ссылку count не равно нулю. *PpvObject* параметру присваивается строгая ссылка.  
  
-   В противном случае — значение HRESULT, указывающее причину этой операции не удалось.  
  
## <a name="remarks"></a>Примечания  
 Устанавливает заданный указатель в текущее значение строгую ссылку, если строгую ссылку count не равно нулю.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** implements.h  
  
 **Пространство имен:** Microsoft::wrl:: Details  
  
## <a name="see-also"></a>См. также  
 [WeakReference Class1](../windows/weakreference-class1.md)   
 [Пространство имен Microsoft::WRL::Details](../windows/microsoft-wrl-details-namespace.md)