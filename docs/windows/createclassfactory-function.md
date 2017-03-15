---
title: "Функция CreateClassFactory | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "module/Microsoft::WRL::Details::CreateClassFactory"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CreateClassFactory - функция"
ms.assetid: 772d5d1b-8872-4745-81ca-521a39564713
caps.latest.revision: 2
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 2
---
# Функция CreateClassFactory
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Создает фабрику, которая создает экземпляры указанного класса.  
  
## Синтаксис  
  
```cpp  
  
template<typename Factory>  
inline HRESULT STDMETHODCALLTYPE CreateClassFactory(  
   _In_ unsigned int *flags,   
   _In_ const CreatorMap* entry,   
   REFIID riid,   
   _Outptr_ IUnknown **ppFactory  
) throw();  
  
```  
  
#### Параметры  
 `flags`  
 Сочетание одного или нескольких значений перечисления [RuntimeClassType](../windows/runtimeclasstype-enumeration.md).  
  
 `entry`  
 Указатель на [CreatorMap](../windows/creatormap-structure.md), содержащий сведения об инициализации и регистрации параметра `riid`.  
  
 `riid`  
 Ссылка на идентификатор интерфейса.  
  
 `ppFactory`  
 Если эта операция завершена успешно, указатель на фабрики класса.  
  
## Возвращаемое значение  
 Значение S\_ОК в случае успеха; в противном случае — значение HRESULT, указывающее на ошибку.  
  
## Примечания  
 Ошибка утверждения создается, если параметр `Factory` шаблона не является производным от интерфейса IClassFactory.  
  
## Требования  
 **Заголовок:** module.h  
  
 **Пространство имен:** Microsoft::WRL  
  
## См. также  
 [Пространство имен Microsoft::WRL::Wrappers::Details](../windows/microsoft-wrl-wrappers-details-namespace.md)