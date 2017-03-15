---
title: "Класс SimpleClassFactory | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "module/Microsoft::WRL::SimpleClassFactory"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "SimpleClassFactory - класс"
ms.assetid: 6edda1b2-4e44-4e14-9364-72f519249962
caps.latest.revision: 4
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 4
---
# Класс SimpleClassFactory
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Предоставляет основной механизм для создания базового класса.  
  
## Синтаксис  
  
```  
template<  
   typename Base  
>  
class SimpleClassFactory : public ClassFactory<>;  
```  
  
#### Параметры  
 `Base`  
 Базовый класс.  
  
## Примечания  
 У базового класса должен быть конструктор по умолчанию.  
  
 В следующем примере кода показано использование SimpleClassFactory с макросом [ActivatableClassWithFactoryEx](../Topic/ActivatableClass%20Macros.md).  
  
 `ActivatableClassWithFactoryEx(MyClass, SimpleClassFactory, MyServerName);`  
  
## Члены  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[Метод SimpleClassFactory::CreateInstance](../windows/simpleclassfactory-createinstance-method.md)|Создает экземпляр указанного интерфейса.|  
  
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
  
 `SimpleClassFactory`  
  
## Требования  
 **Заголовок:** module.h  
  
 **Пространство имен:** Microsoft::WRL  
  
## См. также  
 [Пространство имен Microsoft::WRL](../windows/microsoft-wrl-namespace.md)