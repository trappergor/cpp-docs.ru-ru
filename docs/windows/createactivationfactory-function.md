---
title: "Функция CreateActivationFactory | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "module/Microsoft::WRL::Details::CreateActivationFactory"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CreateActivationFactory - функция"
ms.assetid: a1a53e04-6757-4faf-a4c8-ecf06e43b959
caps.latest.revision: 2
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 2
---
# Функция CreateActivationFactory
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Создает фабрику, которая производит экземпляры указанного класса, которые могут быть активированы средой выполнения Windows.  
  
## Синтаксис  
  
```cpp  
  
template<typename Factory>  
   inline HRESULT STDMETHODCALLTYPE CreateActivationFactory(  
      _In_ unsigned int *flags,    
      _In_ const CreatorMap* entry,   
      REFIID riid,   
     _Outptr_ IUnknown **ppFactory) throw();  
  
```  
  
#### Параметры  
 `flags`  
 Сочетание одного или нескольких значений перечисления [RuntimeClassType](../windows/runtimeclasstype-enumeration.md).  
  
 `entry`  
 Указатель на [CreatorMap](../windows/creatormap-structure.md), содержащий сведения об инициализации и регистрации параметра `riid`.  
  
 `riid`  
 Ссылка на идентификатор интерфейса.  
  
 `ppFactory`  
 Если эта операция завершается успешно, то указатель на фабрику активации.  
  
## Возвращаемое значение  
 Значение S\_ОК в случае успеха; в противном случае — значение HRESULT, указывающее на ошибку.  
  
## Примечания  
 Ошибка утверждения создается, если параметр `Factory` шаблона не является производным от интерфейса IActivationFactory.  
  
## Требования  
 **Заголовок:** module.h  
  
 **Пространство имен:** Microsoft::WRL  
  
## См. также  
 [Пространство имен Microsoft::WRL::Wrappers::Details](../windows/microsoft-wrl-wrappers-details-namespace.md)