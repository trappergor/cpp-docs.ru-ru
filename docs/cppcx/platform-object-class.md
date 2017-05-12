---
title: "Класс Platform::Object | Microsoft Docs"
ms.custom: ""
ms.date: "12/30/2016"
ms.prod: "windows-client-threshold"
ms.technology: ""
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "Platform/Platform::Object"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Object - класс"
ms.assetid: 709e84a8-0bff-471b-bc14-63e424080b5a
caps.latest.revision: 9
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
caps.handback.revision: 9
---
# Класс Platform::Object
Определяет общее поведение для классов ссылок и структур ссылок в приложениях для Магазина Windows. Все экземпляры классов ссылок и структур ссылок могут неявно преобразовываться в Platform::Object^ и переопределять его виртуальный метод ToString.  
  
## Синтаксис  
  
```scr  
public ref class Object : Object  
```  
  
## Члены  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|[Конструктор Object::Object](../cppcx/object-object-constructor.md)|Инициализирует новый экземпляр класса Object.|  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[Метод Object::Equals](../cppcx/object-equals-method.md)|Определяет, равен ли заданный объект текущему объекту.|  
|[Метод Object::GetHashCode](../cppcx/object-gethashcode-method.md)|Возвращает хэш\-код данного экземпляра.|  
|[Метод Object::ReferenceEquals](../cppcx/object-referenceequals-method.md)|Определяет, являются ли указанные экземпляры класса Object одним и тем же экземпляром.|  
|[Метод ToString](../cppcx/object-tostring-method-c-cx.md)|Возвращает строку, представляющую текущий объект. Может быть переопределен.|  
|[Метод GetType](../cppcx/object-gettype-method.md)|Получает объект [Platform::Type](../cppcx/platform-type-class.md), описывающий текущий экземпляр.|  
  
## Иерархия наследования  
 `Object`  
  
 `Object`  
  
## Требования  
 **Заголовок:** vccorlib.h  
  
 **Пространство имен:** Platform  
  
## См. также  
 [\(NOTINBUILD\) Пространство имен Platform](http://msdn.microsoft.com/ru-ru/f3ce3eab-028c-4204-ba9f-9ab8af17c8c4)