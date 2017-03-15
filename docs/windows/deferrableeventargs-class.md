---
title: "Класс DeferrableEventArgs | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
dev_langs: 
  - "C++"
ms.assetid: ece89267-7b72-40e1-8185-550c865b070a
caps.latest.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 3
---
# Класс DeferrableEventArgs
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Класс шаблона, используемый для типов аргументов событий для задержек.  
  
## Синтаксис  
  
```cpp  
template <  
typename TEventArgsInterface,  
typename TEventArgsClass  
>  
class DeferrableEventArgs : public TEventArgsInterface  
  
```  
  
#### Параметры  
 `TEventArgsInterface`  
 Тип интерфейса, который объявляет аргументы для отложенного события.  
  
 `TEventArgsClass`  
 Класс, который реализует `TEventArgsInterface`.  
  
## Участники  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[Метод DeferrableEventArgs::GetDeferral](../windows/deferrableeventargs-getdeferral-method.md)|Возвращает ссылку на объект [Задержка](http://go.microsoft.com/fwlink/?LinkId=526520), который представляет отложенное событие.|  
|[Метод DeferrableEventArgs::InvokeAllFinished](../windows/deferrableeventargs-invokeallfinished-method.md)|Вызывается, чтобы указать, что вся обработка для отложенного события завершена.|  
  
## Заметки  
 Экземпляры этого класса передаются в обработчики событий для отложенных событий.  Параметры шаблона представляют интерфейс, определяющий подробные сведения об аргументах событий для конкретного типа отложенного события, а также класс, реализующий этот интерфейс.  
  
 Класс отображается как первый аргумент обработчика событий для отложенного события.  Чтобы получить объект [Задержка](http://go.microsoft.com/fwlink/?LinkId=526520), из которого можно получить все сведения об отложенном событии, можно вызвать метод [GetDeferral](../windows/deferrableeventargs-getdeferral-method.md).  После завершения обработки событий необходимо вызвать завершение в объекте «Задержка».  Затем следует вызвать [InvokeAllFinished](../windows/deferrableeventargs-invokeallfinished-method.md) в конце метода обработчика событий. Это гарантирует, что сведения о завершении всех отложенных событий будут передаваться должным образом.  
  
## Требования  
 **Заголовок:** event.h  
  
 **Пространство имен:** Microsoft::WRL  
  
## См. также  
 [Пространство имен Microsoft::WRL](../windows/microsoft-wrl-namespace.md)