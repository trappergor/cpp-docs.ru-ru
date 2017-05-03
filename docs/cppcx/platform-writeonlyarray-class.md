---
title: "Класс Platform::WriteOnlyArray | Microsoft Docs"
ms.custom: ""
ms.date: "12/30/2016"
ms.prod: "windows-client-threshold"
ms.technology: ""
ms.reviewer: ""
s.suite: 
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "Platform/Platform::WriteOnlyArray"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Класс Platform::WriteOnlyArray"
ms.assetid: 92d7dd56-ec58-4b8c-88ba-9c903668b687
caps.latest.revision: 11
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
caps.handback.revision: 11
---
# Класс Platform::WriteOnlyArray
Представляет одномерный массив, который используется в качестве входного параметра, когда вызывающая сторона передает массив в метод для заполнения.  
  
 Этот класс ссылок объявлен в vccorlib.h как закрытый; следовательно, он не передается в метаданные и использовать его можно только из С\+\+. Этот класс предназначен для использования только в качестве входного параметра, который получает массив, выделенный вызывающим объектом. Его невозможно построить из пользовательского кода. Оно позволяет методу C\+\+ осуществлять запись непосредственно в этот массив — шаблон, известный как *FillArray*. Для получения дополнительной информации см. [Классы Array и WriteOnlyArray](../cppcx/array-and-writeonlyarray-c-cx.md).  
  
## Синтаксис  
  
```cpp  
private ref class WriteOnlyArray<T, 1>  
```  
  
## Участники  
  
### Открытые методы  
 Эти методы имеют внутреннюю доступность, то есть доступны только в компоненте или приложении С\+\+.  
  
|Имя|Описание|  
|---------|--------------|  
|[Метод WriteOnlyArray::begin](../cppcx/writeonlyarray-begin-method.md)|Итератор, который указывает на первый элемент массива.|  
|[Свойство WriteOnlyArray::Data](../cppcx/writeonlyarray-data-property.md)|Указатель на буфер данных.|  
|[Метод WriteOnlyArray::end](../cppcx/writeonlyarray-end-method.md)|Итератор, указывающий на элемент, следующий за последним элементом в массиве.|  
|[Свойство WriteOnlyArray::FastPass](../cppcx/writeonlyarray-fastpass-property.md)|Указывает, сможет ли массив использовать механизм FastPass, то есть прозрачную оптимизацию, выполняемую системой. Не используйте его в коде|  
|[Свойство WriteOnlyArray::Length](../cppcx/writeonlyarray-length-property.md)|Возвращает число элементов в массиве.|  
|[Функция WriteOnlyArray::set](../cppcx/writeonlyarray-set-function.md)|Присваивает заданному элементу заданное значение.|  
  
## Иерархия наследования  
 `WriteOnlyArray`  
  
## Требования  
 Параметр компилятора: **\/ZW**  
  
 **Метаданные:** Platform.winmd  
  
 **Пространство имен:** Platform  
  
## См. также  
 [\(NOTINBUILD\) Пространство имен Platform](http://msdn.microsoft.com/ru-ru/f3ce3eab-028c-4204-ba9f-9ab8af17c8c4)   
 [Создание компонентов среды выполнения Windows в C\+\+](../Topic/Creating%20Windows%20Runtime%20Components%20in%20C++.md)