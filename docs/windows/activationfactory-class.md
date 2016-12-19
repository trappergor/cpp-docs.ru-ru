---
title: "Класс ActivationFactory | Microsoft Docs"
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
  - "module/Microsoft::WRL::ActivationFactory"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ActivationFactory - класс"
ms.assetid: 5faddf1f-43b6-4f8a-97de-8c9d3ae1e1ff
caps.latest.revision: 4
caps.handback.revision: 4
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Класс ActivationFactory
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Позволяет одному или нескольким классам быть активированными средой выполнения Windows.  
  
## Синтаксис  
  
```  
template <  
   typename I0 = Details::Nil,  
   typename I1 = Details::Nil,  
   typename I2 = Details::Nil  
>  
class ActivationFactory : public Details::RuntimeClass<typename Details::InterfaceListHelper<IActivationFactory, I0, I1, I2, Details::Nil>::TypeT, RuntimeClassFlags<WinRt | InhibitWeakReference>, false>;  
```  
  
#### Параметры  
 `I0`  
 Нулевой интерфейс.  
  
 `I1`  
 Первый интерфейс.  
  
 `I2`  
 Второй интерфейс.  
  
## Примечания  
 ActivationFactory предоставляет методы регистрации и основные функциональные возможности для интерфейса IActivationFactory.  ActivationFactory также позволяет задать пользовательскую реализацию фабрики.  
  
 В следующем фрагменте кода символически показано, как использовать ActivationFactory.  
  
 [!code-cpp[wrl-microsoft__wrl__activationfactory#1](../windows/codesnippet/CPP/activationfactory-class_1.cpp)]  
  
 В следующем фрагменте кода показано, как использовать структуру [Implements](../Topic/Implements%20Structure.md) для указания более трех идентификаторов интерфейса.  
  
 `struct MyFactory : ActivationFactory<Implements<I1, I2, I3>, I4, I5>;`  
  
## Члены  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|[Конструктор ActivationFactory::ActivationFactory](../windows/activationfactory-activationfactory-constructor.md)|Инициализирует класс ActivationFactory.|  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[Метод ActivationFactory::AddRef](../windows/activationfactory-addref-method.md)|Увеличивает значение счетчика ссылок для текущего объекта ActivationFactory.|  
|[Метод ActivationFactory::GetIids](../windows/activationfactory-getiids-method.md)|Извлекает массив идентификаторов реализованного интерфейса.|  
|[Метод ActivationFactory::GetRuntimeClassName](../windows/activationfactory-getruntimeclassname-method.md)|Возвращает имя класса среды выполнения для объекта, который создает текущий ActivationFactory.|  
|[Метод ActivationFactory::GetTrustLevel](../windows/activationfactory-gettrustlevel-method.md)|Получает уровень доверия объекта, который инициализируется текущим ActivationFactory.|  
|[Метод ActivationFactory::QueryInterface](../windows/activationfactory-queryinterface-method.md)|Извлекает указатель на заданный интерфейс.|  
|[Метод ActivationFactory::Release](../windows/activationfactory-release-method.md)|Уменьшает значение счетчика ссылок для текущего объекта ActivationFactory.|  
  
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
  
 `ActivationFactory`  
  
## Требования  
 **Заголовок:** module.h  
  
 **Пространство имен:** Microsoft::WRL  
  
## См. также  
 [Пространство имен Microsoft::WRL](../windows/microsoft-wrl-namespace.md)