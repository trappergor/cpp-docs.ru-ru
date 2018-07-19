---
title: SafeInt::SafeInt | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- SafeInt::SafeInt
- SafeInt
- SafeInt.SafeInt
dev_langs:
- C++
helpviewer_keywords:
- SafeInt class, constructor
ms.assetid: 39e6f632-a396-40e6-9ece-cc3d4c5a78ef
author: ghogen
ms.author: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: c7154349105c1953ad314b7928e7be8385179c42
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2018
ms.locfileid: "33888751"
---
# <a name="safeintsafeint"></a>SafeInt::SafeInt
Создает объект `SafeInt`.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
SafeInt() throw  
  
SafeInt (  
   const T& i  
) throw ()  
  
SafeInt (  
   bool b  
) throw ()  
  
template <typename U>  
SafeInt (  
   const SafeInt <U, E>& u  
)  
  
I template <typename U>  
SafeInt (  
   const U& i  
)  
```  
  
#### <a name="parameters"></a>Параметры  
 [in] `i`  
 Значение для нового `SafeInt` объекта. Это должен быть параметр типа T или U, в зависимости от конструктора.  
  
 [in] `b`  
 Логическое значение для нового `SafeInt` объекта.  
  
 [in] `u`  
 Объект `SafeInt` типа u. Новый `SafeInt` объект будет иметь то же значение, что `u`, но будет типа T.  
  
 U  
 Тип данных, хранящихся в `SafeInt`. Это может быть значение типа Boolean, символьного или целочисленного типа. Если это целочисленный тип, можно будет подписанные или неподписанные и находиться в диапазоне от 8 до 64 бит.  
  
## <a name="remarks"></a>Примечания  
 Дополнительные сведения о типах шаблонов `T` и `E`, в разделе [класс SafeInt](../windows/safeint-class.md).  
  
 Входной параметр для конструктора `i` или `u`, должно быть логическое значение, символьного или целочисленного типа. Если это другой тип параметра, `SafeInt` класса вызывает [static_assert](../cpp/static-assert.md) указывает недопустимый входной параметр.  
  
 Конструкторы, которые используют тип шаблона `U` автоматически преобразует входной параметр в тип, заданный параметром `T`. `SafeInt` Класс преобразует данных без потери данных. Сообщает обработчик ошибок `E` если его не удается преобразовать в тип данных `T` без потери данных.  
  
 Если вы создаете `SafeInt` от логического параметра, необходимо инициализировать значение немедленно. Не удается создать `SafeInt` с помощью кода `SafeInt<bool> sb;`. Это будет выдана ошибка компиляции.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** safeint.h  
  
 **Пространство имен:** msl::utilities  
  
## <a name="see-also"></a>См. также  
 [Библиотека SafeInt](../windows/safeint-library.md)   
 [SafeInt-класс](../windows/safeint-class.md)   
 [Класс SafeIntException](../windows/safeintexception-class.md)