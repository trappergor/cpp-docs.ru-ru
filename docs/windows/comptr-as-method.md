---
title: Метод ComPtr::As | Документация Майкрософт
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
ms.openlocfilehash: debf10e3c3d7ca68bd277a32e55c21b3e8bf3421
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/08/2018
ms.locfileid: "39645429"
---
# <a name="comptras-method"></a>Метод ComPtr::As
Возвращает **ComPtr** , представляющий интерфейс, определенный параметром указанного шаблона.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
template<typename U>  
HRESULT As(  
   _Out_ ComPtr<U>* p  
) const;  
  
template<typename U>  
HRESULT As(  
   _Out_ Details::ComPtrRef<ComPtr<U>> p  
) const;  
```  
  
### <a name="parameters"></a>Параметры  
 *U*  
 Интерфейс для представления параметром *p*.  
  
 *p*  
 Объект **ComPtr** объект, представляющий интерфейс, заданный параметром *U*. Параметр *p* не должен ссылаться на текущий **ComPtr** объекта.  
  
## <a name="remarks"></a>Примечания  
 Первый шаблон — это форма, которую необходимо использовать в коде. Второй шаблон является внутренней вспомогательной специализацией, которая поддерживает функции языка C++, например ключевое слово выведения типа [auto](../cpp/auto-cpp.md) .  
  
## <a name="return-value"></a>Возвращаемое значение  
 Значение S_OK, если операция завершилась успешно; в противном случае — значение HRESULT, указывающее на ошибку.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** client.h  
  
 **Пространство имен:** Microsoft::WRL  
  
## <a name="see-also"></a>См. также  
 [Класс ComPtr](../windows/comptr-class.md)