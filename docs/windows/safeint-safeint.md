---
title: "SafeInt::SafeInt | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "SafeInt::SafeInt"
  - "SafeInt"
  - "SafeInt.SafeInt"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "SafeInt - класс, конструктор"
ms.assetid: 39e6f632-a396-40e6-9ece-cc3d4c5a78ef
caps.latest.revision: 7
caps.handback.revision: 7
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# SafeInt::SafeInt
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Создает объект `SafeInt`.  
  
## Синтаксис  
  
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
  
#### Параметры  
 \[входящий\] `i`  
 Значение для нового объекта `SafeInt`.  Это должно быть параметром типа T или U, в зависимости от конструктора.  
  
 \[входящий\] `b`  
 Логическое значение для нового объекта `SafeInt`.  
  
 \[входящий\] `u`  
 `SafeInt` типа U.  Новый объект `SafeInt` будет иметь то же значение, что и `u`, но будет типа T.  
  
 U  
 Тип данных, хранящихся в `SafeInt`.  Это может быть либо логическим, символом или знака.  Если целочисленный тип, то он может подписываться или удаления и содержать от 8 до 64 бита.  
  
## Заметки  
 Дополнительные сведения о типах `T` и `E` шаблона см. в разделе [Класс SafeInt](../windows/safeint-class.md).  
  
 Входной параметр для конструктора, `i` или `u`, должен быть логическим, символом или знака.  Если другой тип параметра, класс `SafeInt` вызывает функцию [static\_assert](../cpp/static-assert.md) для указания недопустимый входной параметр.  
  
 Конструкторы, которые используют тип `U` шаблона автоматически преобразуют входной параметр к типу, указанному `T`.  Класс `SafeInt` преобразования данных без каких\-либо потери данных.  Он отчеты в обработчик ошибок `E`, если она не может преобразовать данные вводить `T` без потери данных.  
  
 При создании `SafeInt` из логического параметра, необходимо инициализировать значение немедленно.  Невозможно создать `SafeInt` с помощью кода `SafeInt<bool> sb;`.  Это вызовет ошибку компилировать.  
  
## Требования  
 **Заголовок:** safeint.h  
  
 **Пространство имен:** msl::utilities  
  
## См. также  
 [Библиотека SafeInt](../windows/safeint-library.md)   
 [Класс SafeInt](../windows/safeint-class.md)   
 [Класс SafeIntException](../windows/safeintexception-class.md)