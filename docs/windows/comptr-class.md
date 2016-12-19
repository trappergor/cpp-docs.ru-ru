---
title: "Класс ComPtr | Microsoft Docs"
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
  - "client/Microsoft::WRL::ComPtr"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Класс ComPtr"
ms.assetid: a6551902-6819-478a-8df7-b6f312ab1fb0
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Класс ComPtr
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Создает тип *интеллектуальный указатель*, который представляет интерфейс, определяемый параметром шаблона. ComPtr автоматически поддерживает счетчик ссылок для указателя базового интерфейса и освобождает интерфейс, когда счетчик ссылок становится равен нулю.  
  
## Синтаксис  
  
```  
template <  
   typename T  
>  
class ComPtr;  
  
template<  
   class U  
>  
friend class ComPtr;  
```  
  
#### Параметры  
 `T`  
 Интерфейс, который представляет класс ComPtr.  
  
 `U`  
 Класс, для которого текущий класс ComPtr является дружественным. \(Шаблон, который использует этот параметр, защищен.\)  
  
## Примечания  
 ComPtr\<\> объявляет тип, представляющий указатель базового интерфейса. ComPtr\<\> можно использовать для объявления переменной, а затем использовать оператор доступа к членам класса в виде стрелки \(`->`\) для доступа к функции\-члену интерфейса.  
  
 Дополнительные сведения об интеллектуальных указателях см. в подразделе "Интеллектуальные указатели COM" статьи [COM Coding Practices](http://msdn.microsoft.com/ru-ru/76aca556-b4d6-4e67-a2a3-4439900f0c39) в библиотеке MSDN.  
  
## Участники  
  
### Общедоступные определения типов  
  
|Имя|Описание|  
|---------|--------------|  
|`InterfaceType`|Синоним типа, указанного параметром шаблона `T`.|  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|[Конструктор ComPtr::ComPtr](../windows/comptr-comptr-constructor.md)|Инициализирует новый экземпляр класса ComPtr. Перегрузки предоставляют конструкторы по умолчанию, конструкторы копирования, перемещения и преобразования.|  
|[Деструктор ComPtr::~ComPtr](../windows/comptr-tilde-comptr-destructor.md)|Отменяет инициализацию экземпляра ComPtr.|  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[Метод ComPtr::As](../windows/comptr-as-method.md)|Возвращает объект ComPtr, представляющий интерфейс, определенный указанным параметром шаблона.|  
|[Метод ComPtr::AsIID](../windows/comptr-asiid-method.md)|Возвращает объект ComPtr, представляющий интерфейс, определенный указанным идентификатором интерфейса.|  
|[Метод ComPtr::AsWeak](../windows/comptr-asweak-method.md)|Извлекает слабую ссылку на текущий объект.|  
|[Метод ComPtr::Attach](../windows/comptr-attach-method.md)|Связывает этот объект ComPtr с типом интерфейса, указанным текущим параметром типа шаблона.|  
|[Метод ComPtr::CopyTo](../windows/comptr-copyto-method.md)|Копирует текущий или указанный интерфейс, связанный с этим объектом ComPtr, в заданный выходной указатель.|  
|[Метод ComPtr::Detach](../Topic/ComPtr::Detach%20Method.md)|Отменяет связь этого объекта ComPtr с интерфейсом, который он представляет.|  
|[Метод ComPtr::Get](../windows/comptr-get-method.md)|Извлекает указатель на интерфейс, который связан с данным объектом ComPtr.|  
|[Метод ComPtr::GetAddressOf](../Topic/ComPtr::GetAddressOf%20Method.md)|Извлекает адрес члена данных [ptr\_](../windows/comptr-ptr-data-member.md), который содержит указатель на интерфейс, представленный этим объектом ComPtr.|  
|[Метод ComPtr::ReleaseAndGetAddressOf](../windows/comptr-releaseandgetaddressof-method.md)|Освобождает интерфейс, связанный с данным объектом ComPtr, а затем извлекает адрес данных\-члена [ptr\_](../windows/comptr-ptr-data-member.md), который содержит указатель на освобожденный интерфейс.|  
|[ComPtr::Reset](../windows/comptr-reset.md)|Освобождает все ссылки на указатель на интерфейс, который связан с данным объектом ComPtr.|  
|[Метод ComPtr::Swap](../windows/comptr-swap-method.md)|Меняет местами интерфейс, управляемый текущим объектом ComPtr с интерфейсом, который управляется указанным объектом ComPtr.|  
  
### Защищенные методы  
  
|Имя|Описание|  
|---------|--------------|  
|[Метод ComPtr::InternalAddRef](../windows/comptr-internaladdref-method.md)|Увеличивает счетчик ссылок интерфейса, связанного с этим объектом ComPtr.|  
|[Метод ComPtr::InternalRelease](../windows/comptr-internalrelease-method.md)|Выполняет операцию освобождения модели COM для интерфейса, связанного с этим объектом ComPtr.|  
  
### Открытые операторы  
  
|Имя|Описание|  
|---------|--------------|  
|[Оператор ComPtr::operator Microsoft::WRL::Details::BoolType](../windows/comptr-operator-microsoft-wrl-details-booltype-operator.md)|Указывает, управляет ли ComPtr временем существования объекта интерфейса.|  
|[Оператор ComPtr::operator&](../windows/comptr-operator-ampersand-operator.md)|Получает адрес текущего объекта ComPtr.|  
|[Оператор ComPtr::operator\=](../windows/comptr-operator-assign-operator.md)|Присваивает значение текущему объекту ComPtr.|  
|[Оператор ComPtr::operator\-\>](../windows/comptr-operator-arrow-operator.md)|Извлекает указатель на тип, заданный текущим параметром шаблона.|  
|[Оператор ComPtr::operator\=\=](../windows/comptr-operator-equality-operator.md)|Определяет равенство двух объектов СomPtr.|  
|[Оператор ComPtr::operator\!\=](../windows/comptr-operator-inequality-operator.md)|Определяет неравенство двух объектов СomPtr.|  
  
### Защищенные члены данных  
  
|Имя|Описание|  
|---------|--------------|  
|[Элемент данных ComPtr::ptr\_](../windows/comptr-ptr-data-member.md)|Содержит указатель на интерфейс, который связан с данным объектом ComPtr и управляется им.|  
  
## Иерархия наследования  
 `ComPtr`  
  
## Требования  
 **Заголовок:** client.h  
  
 **Пространство имен:** Microsoft::WRL  
  
## См. также  
 [Пространство имен Microsoft::WRL](../windows/microsoft-wrl-namespace.md)