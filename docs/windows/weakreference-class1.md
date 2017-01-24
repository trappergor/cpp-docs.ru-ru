---
title: "Класс WeakReference | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "implements/Microsoft::WRL::Details::WeakReference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "WeakReference - класс"
ms.assetid: 3f4c956b-dbbd-49b1-8cfa-9509a9956c97
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Класс WeakReference
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Предназначено для поддержки инфраструктуры WRL, а не для непосредственного использования в коде.  
  
## Синтаксис  
  
```  
class WeakReference;  
```  
  
## Примечания  
 Представляет собой *слабую ссылку*, которую можно использовать со средой выполнения Windows или классической моделью COM.  Слабая ссылка представляет собой объект, который может быть доступен или недоступен.  
  
 Объект `WeakReference` поддерживает *строгую ссылку*, которая является указателем на объект, и *число строгих ссылок*, это число копий строгой ссылки, которые распределялись методом Resolve\(\).  Пока число строгих ссылок отлично от нуля, строгая ссылка является действительной и объект доступен.  Когда количество строгих ссылок становится равно нулю, строгая ссылка становится недействительной и объект становится недоступен.  
  
 Объект WeakReference обычно используется для представления объекта, наличием которого управляет внешний поток или приложение.  Например, создайте объект WeakReference из ссылки на объект файла.  Пока открыт файл, строгая ссылка является действительной.  Но если файл закрыт, строгая ссылка станет недействительной.  
  
 Методы WeakReference являются потокобезопасными.  
  
## Члены  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|[Конструктор WeakReference::WeakReference](../windows/weakreference-weakreference-constructor.md)|Инициализирует новый экземпляр класса WeakReference.|  
|[Деструктор WeakReference::~WeakReference](../windows/weakreference-tilde-weakreference-destructor.md)|Деинициализирует \(уничтожает\) текущий экземпляр класса WeakReference.|  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[Метод WeakReference::DecrementStrongReference](../Topic/WeakReference::DecrementStrongReference%20Method.md)|Уменьшает значение счетчика строгих ссылок текущего объекта WeakReference.|  
|[Метод WeakReference::IncrementStrongReference](../windows/weakreference-incrementstrongreference-method.md)|Увеличивает значение счетчика строгих ссылок текущего объекта WeakReference.|  
|[Метод WeakReference::Resolve](../windows/weakreference-resolve-method.md)|Задает определенный указатель на значение текущей строгой ссылки, если число строгих ссылок отлично от нуля.|  
|[Метод WeakReference::SetUnknown](../windows/weakreference-setunknown-method.md)|Устанавливает строгую ссылку текущего объекта WeakReference на определенный указатель интерфейса.|  
  
## Иерархия наследования  
 `WeakReference`  
  
## Требования  
 **Заголовок:** implements.h  
  
 **Пространство имен:** Microsoft::WRL::Details  
  
## См. также  
 [Пространство имен Microsoft::WRL::Details](../windows/microsoft-wrl-details-namespace.md)