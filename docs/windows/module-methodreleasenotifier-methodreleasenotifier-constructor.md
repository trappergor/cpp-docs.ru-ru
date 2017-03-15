---
title: "Конструктор Module::MethodReleaseNotifier::MethodReleaseNotifier | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "module/Microsoft::WRL::Module::MethodReleaseNotifier::MethodReleaseNotifier"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "MethodReleaseNotifier, конструктор"
ms.assetid: 762e2ca4-0a92-49de-9ff5-d3efa0f067c0
caps.latest.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 3
---
# Конструктор Module::MethodReleaseNotifier::MethodReleaseNotifier
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Инициализирует новый экземпляр класса Module::MethodReleaseNotifier.  
  
## Синтаксис  
  
```  
  
MethodReleaseNotifier(  
   _In_ T* object,   
   _In_ void (T::* method)(),   
   bool release) throw() :  
            ReleaseNotifier(release), object_(object),   
            method_(method);  
```  
  
#### Параметры  
 `object`  
 Объект, функция\-член которого является обработчиком событий.  
  
 `method`  
 Функция\-член параметра `object`, которая является обработчиком событий.  
  
 `release`  
 Укажите `true` чтобы включить для вызова базового метода [Module::ReleaseNotifier::Release\(\)](../windows/module-releasenotifier-release.md); в противном случае укажите `false`.  
  
## Требования  
 **Заголовок:** module.h  
  
 **Пространство имен:** Microsoft::WRL  
  
## См. также  
 [Класс Module::MethodReleaseNotifier](../Topic/Module::MethodReleaseNotifier%20Class.md)