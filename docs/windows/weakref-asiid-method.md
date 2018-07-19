---
title: Метод WeakRef::AsIID | Документы Microsoft
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
ms.openlocfilehash: 69108681b181d0b2fce20f9e30a009b6b93c2180
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2018
ms.locfileid: "33891302"
---
# <a name="weakrefasiid-method"></a>Метод WeakRef::AsIID
Задает определенный указатель ComPtr для представления идентификатора указанного интерфейса.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT AsIID(  
   REFIID riid,  
   _Out_ ComPtr<IInspectable>* ptr  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `riid`  
 Идентификатор интерфейса.  
  
 `ptr`  
 Когда эта операция завершается, объект, представляющий параметр `riid`.  
  
## <a name="return-value"></a>Возвращаемое значение  
  
-   Значение S_OK, если операция завершилась успешно; в противном случае — значение HRESULT, указывающее на причину неудачного завершения операции, а `ptr` устанавливается в значение `nullptr`.  
  
-   Значение S_ОК, если операция завершилась успешно, но текущий объект WeakRef уже был выпущен. Параметр `ptr` устанавливается в значение `nullptr`.  
  
-   Значение S_OK, если операция завершилась успешно, но текущий объект WeakRef не получен из параметра `riid`. Параметр `ptr` устанавливается в значение `nullptr`. (Дополнительные сведения см. в разделе "Примечания".)  
  
## <a name="remarks"></a>Примечания  
 Ошибка создается, если параметр `riid` не получен из IInspectable. Эта ошибка заменяет возвращаемое значение.  
  
 Первый шаблон — это форма, которую необходимо использовать в коде. Второй шаблон (не показанный здесь, но объявленный в файле заголовка) является внутренней вспомогательной специализацией, которая поддерживает функции языка C++, например ключевое слово выведения типа [auto](../cpp/auto-cpp.md) .  
  
 Начиная с пакета SDK для Windows 10 этот метод не устанавливает экземпляр WeakRef в значение `nullptr` , если не удалось получить слабую ссылку, поэтому следует избегать использования кода проверки ошибок, который проверяет наличие `nullptr`для WeakRef. Вместо этого проверьте `ptr` для `nullptr`.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** client.h  
  
 **Пространство имен:** Microsoft::WRL  
  
## <a name="see-also"></a>См. также  
 [Класс WeakRef](../windows/weakref-class.md)