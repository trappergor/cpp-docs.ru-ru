---
title: Метод WeakRef::AsIID | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- client/Microsoft::WRL::WeakRef::AsIID
dev_langs:
- C++
helpviewer_keywords:
- AsIID method
ms.assetid: 94e87309-32da-4dbb-8233-e77313a1f448
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 60d2900876d7a9fbee7a193d0575bf3afdf4335b
ms.sourcegitcommit: 38af5a1bf35249f0a51e3aafc6e4077859c8f0d9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/09/2018
ms.locfileid: "40012184"
---
# <a name="weakrefasiid-method"></a>Метод WeakRef::AsIID
Задает указанный `ComPtr` параметр-указатель для представления идентификатора указанного интерфейса.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT AsIID(  
   REFIID riid,  
   _Out_ ComPtr<IInspectable>* ptr  
);  
```  
  
### <a name="parameters"></a>Параметры  
 *riid*  
 Идентификатор интерфейса.  
  
 *ptr*  
 После завершения операции, объект, представляющий параметр *riid*.  
  
## <a name="return-value"></a>Возвращаемое значение  
  
-   Значение S_OK, если операция завершилась успешно; в противном случае — значение HRESULT, указывающее причину произошел сбой операции, и *ptr* присваивается **nullptr**.  
  
-   Значение S_OK, если операция завершилась успешно, но текущий **WeakRef** объект уже был выпущен. Параметр *ptr* присваивается **nullptr**.  
  
-   Значение S_OK, если операция завершилась успешно, но текущий **WeakRef** объект не является производным от параметра *riid*. Параметр *ptr* присваивается **nullptr**. (Дополнительные сведения см. в разделе "Примечания".)  
  
## <a name="remarks"></a>Примечания  
 Ошибка создается в том случае, если параметр *riid* не является производным от `IInspectable`. Эта ошибка заменяет возвращаемое значение.  
  
 Первый шаблон — это форма, которую необходимо использовать в коде. Второй шаблон (не показанный здесь, но объявленный в файле заголовка) является внутренней вспомогательной специализацией, которая поддерживает функции языка C++, например ключевое слово выведения типа [auto](../cpp/auto-cpp.md) .  
  
 Начиная с пакета SDK для Windows 10, этот метод устанавливает **WeakRef** экземпляр **nullptr** Если не удалось получить слабую ссылку, поэтому следует избегать кода проверки ошибок, которое проверяет **WeakRef** для **nullptr**. Вместо этого проверьте *ptr* для **nullptr**.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** client.h  
  
 **Пространство имен:** Microsoft::WRL  
  
## <a name="see-also"></a>См. также  
 [Класс WeakRef](../windows/weakref-class.md)