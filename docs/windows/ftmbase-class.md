---
title: "Класс FtmBase | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "ftm/Microsoft::WRL::FtmBase"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "FtmBase - класс"
ms.assetid: 275f3b71-2975-4f92-89e7-d351e96496df
caps.latest.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 3
---
# Класс FtmBase
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Представляет объект маршаллера в режиме свободного потока.  
  
## Синтаксис  
  
```  
  
class FtmBase : public Microsoft::WRL::Implements<  
   Microsoft::WRL::RuntimeClassFlags< WinRtClassicComMix >,   
   Microsoft::WRL::CloakedIid< IMarshal > >;  
```  
  
## Примечания  
 Дополнительные сведения см. в разделе «IMarshal» в подразделе «Интерфейсы модели COM» раздела «Справка по модели COM» в библиотеке MSDN.  
  
## Члены  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|[Конструктор FtmBase::FtmBase](../windows/ftmbase-ftmbase-constructor.md)|Инициализирует новый экземпляр класса FtmBase.|  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[Метод FtmBase::CreateGlobalInterfaceTable](../windows/ftmbase-createglobalinterfacetable-method.md)|Создает глобальную таблицу интерфейсов \(GIT\).|  
|[Метод FtmBase::DisconnectObject](../windows/ftmbase-disconnectobject-method.md)|Принудительно освобождает все внешние подключения к объекту.  Сервер объекта вызывает реализацию этого метода объекта до завершения работы.|  
|[Метод FtmBase::GetMarshalSizeMax](../windows/ftmbase-getmarshalsizemax-method.md)|Получите количество байт, задающих верхнюю границу, необходимую для маршалирования заданного указателя интерфейсов в указанном объекте.|  
|[Метод FtmBase::GetUnmarshalClass](../windows/ftmbase-getunmarshalclass-method.md)|Получает CLSID, который модель COM использует для поиска библиотеки DLL, содержащей код для соответствующей прокси.  Модель COM загружает эту библиотеку DLL для создания неинициализированного экземпляра прокси\-сервера.|  
|[Метод FtmBase::MarshalInterface](../Topic/FtmBase::MarshalInterface%20Method.md)|Записывает в поток данные, необходимые для инициализации объекта прокси\-сервера в некотором процессе клиента.|  
|[Метод FtmBase::ReleaseMarshalData](../Topic/FtmBase::ReleaseMarshalData%20Method.md)|Уничтожает пакет упакованных данных.|  
|[Метод FtmBase::UnmarshalInterface](../windows/ftmbase-unmarshalinterface-method.md)|Инициализирует вновь созданный прокси\-сервер и возвращает указатель интерфейса к этому прокси\-серверу.|  
  
### Открытые члены данных  
  
|Имя|Описание|  
|---------|--------------|  
|[Элемент данных FtmBase::marshaller\_](../windows/ftmbase-marshaller-data-member.md)|Содержит ссылку на маршаллер в режиме свободного потока.|  
  
## Иерархия наследования  
 `FtmBase`  
  
## Требования  
 **Заголовок:** ftm.h  
  
 **Пространство имен:** Microsoft::WRL  
  
## См. также  
 [Пространство имен Microsoft::WRL](../windows/microsoft-wrl-namespace.md)