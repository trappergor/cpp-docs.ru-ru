---
title: "SafeInt::SafeInt | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- SafeInt::SafeInt
- SafeInt
- SafeInt.SafeInt
dev_langs: C++
helpviewer_keywords: SafeInt class, constructor
ms.assetid: 39e6f632-a396-40e6-9ece-cc3d4c5a78ef
caps.latest.revision: "7"
author: ghogen
ms.author: ghogen
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: a9820227384866cdb1a6470ebd9650187848334c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
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