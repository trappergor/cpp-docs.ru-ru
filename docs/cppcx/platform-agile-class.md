---
title: "Класс Platform::Agile | Microsoft Docs"
ms.custom: ""
ms.date: "12/30/2016"
ms.prod: "windows-client-threshold"
ms.technology: ""
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "agile/Platform::Agile"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Platform::Agile"
ms.assetid: e34459a9-c429-4c79-97fd-030c43ca4155
caps.latest.revision: 4
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
caps.handback.revision: 4
---
# Класс Platform::Agile
Представляет объект, имеющий MashalingBehavior \= Standard, как объект Agile, который значительно снижает вероятность возникновения в среде выполнения исключений, связанных с потоками.`Agile<T>` позволяет объекту, отличному от Agile, вызывать тот же или другой поток или быть вызванным из этих потоков. Дополнительные сведения см. в разделе [Работа с потоками и маршалинг](../cppcx/threading-and-marshaling-c-cx.md).  
  
## Синтаксис  
  
```scr  
  
template <typename T>  
    class Agile  
;  
```  
  
#### Параметры  
 T  
 Имя типа для класса, отличного от Agile.  
  
## Заметки  
 Большинство классов в [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] являются классами гибкой разработки \(agile\). Объект Agile может вызывать внутрипроцессный или внепроцессный объект либо быть вызванным таким объектом в том же или другом потоке. Если объект не является объектом гибкой разработки, заключите его в объект `Agile<T>`, который является объектом гибкой разработки. После этого объект `Agile<T>` можно маршалировать, используя таким образом базовый объект, отличный от Agile.  
  
 Класс `Agile<T>` — это стандартный класс неуправляемого кода C\+\+, для которого требуется включаемый файл `agile.h`. Он представляет объект, отличный от Agile, и *контекст* объекта Agile. Контекст задает потоковую модель объекта Agile и поведение маршалинга. Операционная система использует контекст для определения способа маршалирования объекта.  
  
## Члены  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|[Конструктор Agile::Agile](../cppcx/agile-agile-constructor.md)|Инициализирует новый экземпляр класса Agile.|  
|[Деструктор Agile::~Agile](../cppcx/agile-tilde-agile-destructor.md)|Ликвидирует текущий экземпляр класса Agile.|  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[Agile::Get](../cppcx/agile-get-method.md)|Возвращает дескриптор объекта, представленного текущим объектом Agile.|  
|[Agile::GetAddressOf](../cppcx/agile-getaddressof-method.md)|Повторно инициализирует текущий объект Agile и возвращает адрес дескриптора для объекта типа `T`.|  
|[Agile::GetAddressOfForInOut](../cppcx/agile-getaddressofforinout-method.md)|Возвращает адрес дескриптора объекта, представленного текущим объектом Agile.|  
|[Agile::Release](../cppcx/agile-release-method.md)|Отменяет базовый объект и контекст текущего объекта Agile.|  
  
### Открытые операторы  
  
|Имя|Описание|  
|---------|--------------|  
|[Agile::operator\-\>](../cppcx/agile-operator-arrow-operator.md)|Извлекает дескриптор объекта, представленного текущим объектом Agile.|  
|[Agile::operator\=](../cppcx/agile-operator-assign-operator.md)|Присваивает указанное значение текущему объекту Agile.|  
  
## Иерархия наследования  
 `Object`  
  
 `Agile`  
  
## Требования  
 **Минимальный поддерживаемый клиент:** [!INCLUDE[win8](../cppcx/includes/win8-md.md)]  
  
 **Минимальный поддерживаемый сервер:** [!INCLUDE[winserver8](../cppcx/includes/winserver8-md.md)]  
  
 **Пространство имен:** Platform  
  
 **Заголовок:** agile.h  
  
## См. также  
 [\(NOTINBUILD\) Пространство имен Platform](http://msdn.microsoft.com/ru-ru/f3ce3eab-028c-4204-ba9f-9ab8af17c8c4)