---
title: Метод ComPtr::As | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- client/Microsoft::WRL::ComPtr::As
dev_langs:
- C++
helpviewer_keywords:
- As method
ms.assetid: 2ad6c262-9bdb-4c59-a330-1af8bcd445cc
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: fb9fd0ff09f6775a95ff881d9f8cbaa3edc61065
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2018
ms.locfileid: "33857276"
---
# <a name="comptras-method"></a>Метод ComPtr::As
Возвращает объект ComPtr, представляющий интерфейс, определенный указанным параметром шаблона.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
template<typename U>  
HRESULT As(  
   _Out_ ComPtr<U>* p  
) const;  
  
template<typename U>  
HRESULT As(  
   _Out_ Details::ComPtrRef<ComPtr<U>> p  
) const;  
  
```  
  
#### <a name="parameters"></a>Параметры  
 `U`  
 Интерфейс для представления параметром `p`.  
  
 `p`  
 Объект ComPtr, представляющий интерфейс, заданный параметром `U`. Параметр `p` не должен ссылаться на текущий объект ComPtr.  
  
## <a name="remarks"></a>Примечания  
 Первый шаблон — это форма, которую необходимо использовать в коде. Второй шаблон является внутренней вспомогательной специализацией, которая поддерживает функции языка C++, например ключевое слово выведения типа [auto](../cpp/auto-cpp.md) .  
  
## <a name="return-value"></a>Возвращаемое значение  
 Значение S_OK, если операция завершилась успешно; в противном случае — значение HRESULT, указывающее на ошибку.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** client.h  
  
 **Пространство имен:** Microsoft::WRL  
  
## <a name="see-also"></a>См. также  
 [Класс ComPtr](../windows/comptr-class.md)