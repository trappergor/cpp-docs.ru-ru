---
title: "Класс ClassFactory | Microsoft Docs"
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
  - "module/Microsoft::WRL::ClassFactory"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ClassFactory - класс"
ms.assetid: f13e6bce-722b-4f18-b7cf-3ffa6345c1db
caps.latest.revision: 4
caps.handback.revision: 4
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Класс ClassFactory
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Реализует базовую функциональность интерфейса IClassFactory.  
  
## Синтаксис  
  
```  
template <  
   typename I0 = Details::Nil,  
   typename I1 = Details::Nil,  
   typename I2 = Details::Nil  
>  
class ClassFactory : public Details::RuntimeClass<  
   typename Details::InterfaceListHelper<IClassFactory,   
   I0,   
   I1,   
   I2,   
   Details::Nil>::TypeT,   
   RuntimeClassFlags<ClassicCom | InhibitWeakReference>,   
      false>;  
```  
  
#### Параметры  
 `I0`  
 Нулевой интерфейс.  
  
 `I1`  
 Первый интерфейс.  
  
 `I2`  
 Второй интерфейс.  
  
## Примечания  
 Используйте `ClassFactory` для указания определенной пользователем реализации фабрики.  
  
 Следующий шаблон программирования демонстрирует использование структуры [Implements](../Topic/Implements%20Structure.md) для указания более трех интерфейсов для фабрики класса.  
  
 `struct MyFactory : ClassFactory<Implements<I1, I2, I3>, I4, I5>`  
  
## Члены  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|[Конструктор ClassFactory::ClassFactory](../Topic/ClassFactory::ClassFactory%20Constructor.md)||  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[Метод ClassFactory::AddRef](../Topic/ClassFactory::AddRef%20Method.md)|Увеличивает значение счетчика ссылок для текущего объекта ClassFactory.|  
|[Метод ClassFactory::LockServer](../windows/classfactory-lockserver-method.md)|Увеличивает или уменьшает число основных объектов, отслеживаемых текущим объектом ClassFactory.|  
|[Метод ClassFactory::QueryInterface](../windows/classfactory-queryinterface-method.md)|Извлекает указатель на интерфейс, указанный параметром.|  
|[Метод ClassFactory::Release](../windows/classfactory-release-method.md)|Уменьшает значение счетчика ссылок для текущего объекта ClassFactory.|  
  
## Иерархия наследования  
 `I0`  
  
 `ChainInterfaces`  
  
 `I0`  
  
 `RuntimeClassBase`  
  
 `ImplementsHelper`  
  
 `DontUseNewUseMake`  
  
 `RuntimeClassFlags`  
  
 `RuntimeClassBaseT`  
  
 `RuntimeClass`  
  
 `ClassFactory`  
  
## Требования  
 **Заголовок:** module.h  
  
 **Пространство имен:** Microsoft::WRL  
  
## См. также  
 [Пространство имен Microsoft::WRL](../windows/microsoft-wrl-namespace.md)   
 [Перечисление RuntimeClassType](../windows/runtimeclasstype-enumeration.md)