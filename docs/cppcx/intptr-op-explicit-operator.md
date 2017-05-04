---
title: "Оператор IntPtr::op_explicit | Microsoft Docs"
ms.custom: ""
ms.date: "02/09/2017"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "Platform/Platform::IntPtr::op_explicit"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Метод IntPtr::op_explicit"
ms.assetid: cc52e9d5-fe73-471b-8cff-d9f684ba6e20
caps.latest.revision: 3
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# Оператор IntPtr::op_explicit
Преобразует указанный параметр в объект IntPtr или указатель на значение IntPtr.  
  
## Синтаксис  
  
```cpp  
static IntPtr::operator IntPtr( void* value1);   static IntPtr::operator IntPtr( int value2);   static IntPtr::operator void*( IntPtr value3 );  
```  
  
#### Параметры  
 value1  
 Указатель на дескриптор или IntPtr.  
  
 value2  
 32\-битовое целое число, которое можно преобразовать в IntPtr.  
  
 value3  
 Объект IntPtr.  
  
## Возвращаемое значение  
 Первый и второй операторы возвращают IntPtr. Третий оператор возвращает указатель на значение, представленное текущим объектом IntPtr.  
  
## Требования  
 **Минимальный поддерживаемый клиент:** [!INCLUDE[win8](../cppcx/includes/win8-md.md)]  
  
 **Минимальный поддерживаемый сервер:** [!INCLUDE[winserver8](../cppcx/includes/winserver8-md.md)]  
  
 **Пространство имен:** Platform  
  
 **Метаданные:** platform.winmd  
  
## См. также  
 [Класс значения Platform::IntPtr](../cppcx/platform-intptr-value-class.md)