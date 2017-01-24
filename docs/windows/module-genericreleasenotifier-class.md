---
title: "Класс Module::GenericReleaseNotifier | Microsoft Docs"
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
  - "module/Microsoft::WRL::Module::GenericReleaseNotifier"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "GenericReleaseNotifier - класс"
ms.assetid: 244a8fbe-f89b-409b-aa65-db3e37f9b125
caps.latest.revision: 5
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Класс Module::GenericReleaseNotifier
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Вызывает обработчик событий при освобождении последнего объекта в текущем модуле. Обработчик событий задается лямбда-выражением, функтором или указателем на функцию.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
template<  
   typename T  
>  
class GenericReleaseNotifier : public ReleaseNotifier;  
```  
  
#### <a name="parameters"></a>Параметры  
 `T`  
 Тип данных-члена, который содержит расположение обработчика событий.  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[Конструктор Module::genericreleasenotifier:: genericreleasenotifier](../Topic/Module::GenericReleaseNotifier::GenericReleaseNotifier%20Constructor.md)|Инициализирует новый экземпляр класса Module::GenericReleaseNotifier.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[Module::GenericReleaseNotifier:: Invoke-метод](../windows/module-genericreleasenotifier-invoke-method.md)|Вызывает обработчик событий, связанный с текущим объектом Module::GenericReleaseNotifier.|  
  
### <a name="protected-data-members"></a>Защищенные члены данных  
  
|Имя|Описание|  
|----------|-----------------|  
|[Элемент данных Module::genericreleasenotifier::](../windows/module-genericreleasenotifier-callback-data-member.md)|Содержит лямбда-выражения, функтор или обработчик событий указателя на функцию, связанный с текущим объектом Module::GenericReleaseNotifier.|  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `ReleaseNotifier`  
  
 `GenericReleaseNotifier`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** module.h  
  
 **Пространство имен:** Microsoft::WRL
 
 ## <a name="see-also"></a>См. также раздел
 [Класс модулей](../windows/module-class.md)