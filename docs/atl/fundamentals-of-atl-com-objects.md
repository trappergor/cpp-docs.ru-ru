---
title: "Fundamentals of ATL COM Objects | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ATL COM objects"
  - "ATL - библиотека, COM"
  - "COM-объекты, ATL - библиотека"
  - "COM, и ATL"
ms.assetid: 0f9c9d98-cc28-45da-89ac-dc94cee422fe
caps.latest.revision: 25
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 20
---
# Fundamentals of ATL COM Objects
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

На следующей иллюстрации показаны связи между классами и интерфейсы, используемые для идентификации com\-объекта библиотеки ATL.  
  
 ![Структура ATL](../atl/media/vc307y1.png "vc307Y1")  
  
> [!NOTE]
>  На этой диаграмме показано, что `CComObject` является производным от `CYourClass` тогда как `CComAggObject` и `CComPolyObject` включают `CYourClass` в качестве переменной члена.  
  
 Существует три способа определения COM\-объект библиотеки ATL.  Стандартный параметр использовать класс `CComObject`, который является производным от `CYourClass`.  Второй параметр создать объединенный объект с помощью класса `CComAggObject`.  Третий параметр использовать класс `CComPolyObject`.  `CComPolyObject` действует как гибридный. он может работать как класс `CComObject` или как класс `CComAggObject` в зависимости от того, как он впервые создается.  Дополнительные сведения об использовании класса `CComPolyObject` см. в разделе [CComPolyObject Class](../atl/reference/ccompolyobject-class.md).  
  
 При использовании стандартного модели COM библиотеки ATL используется 2 объекта: внешний объект и внутренний объект.  Внешние клиенты получают доступ к функциональности внутреннего объекта до функция\-оболочки, определенные во внешнем объекте.  Внешний объект типа `CComObject`.  
  
 При использовании объединенный объект, внешний объект не предоставляет программы\-оболочки для получения функциональности внутреннего объекта.  Вместо этого внешний объект содержит указатель, непосредственно обратиться к внешнему клиентами.  В этом сценарии внешний объект типа `CComAggObject`.  Внутренний объект переменную\-член внешнего объекта и его типа `CYourClass`.  
  
 Поскольку клиент не должен пройти по внешнему объекту взаимодействовать с внутренним объектом, агрегированные объекты обычно является более эффективным.  Кроме того, внешний объект не должен знать указанного функциональные возможности объединенного объекта, что интерфейс объединенного объекта непосредственно доступен клиенту.  Однако не все объекты могут быть агрегированными.  Для объекта для статистической обработки, для этого нужно конструированным с агрегатом.  
  
 Библиотеки ATL реализует [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509) в 2 действия.  
  
-   Средства [CComObject](../atl/reference/ccomobject-class.md), [CComAggObject](../atl/reference/ccomaggobject-class.md) или [CComPolyObject](../atl/reference/ccompolyobject-class.md) методы **IUnknown**.  
  
-   [CComObjectRoot](../atl/reference/ccomobjectroot-class.md) или [CComObjectRootEx](../atl/reference/ccomobjectrootex-class.md) управляют счетчик ссылок и внешний указатели **IUnknown**.  
  
 Другие аспекты своего COM\-объект библиотеки ATL корректируются другими классами:  
  
-   [CComCoClass](../Topic/CComCoClass%20Class.md) определяет модель фабрики классов и статистической обработки объекта по умолчанию.  
  
-   [IDispatchImpl](../atl/reference/idispatchimpl-class.md) предоставляет реализацию по умолчанию части `IDispatch Interface` всех повторяющихся интерфейсов объекта.  
  
-   [ISupportErrorInfoImpl](../atl/reference/isupporterrorinfoimpl-class.md) реализует интерфейс **ISupportErrorInfo**  который сведения об ошибках могут распространяться по цепочке вызовов правильно.  
  
## Содержание  
 [Реализация CComObjectRootEx](../Topic/Implementing%20CComObjectRootEx.md)  
 Отображение записи сопоставления модели COM примере для реализации `CComObjectRootEx`.  
  
 [Реализация CComObject, CComAggObject и CComPolyObject](../atl/implementing-ccomobject-ccomaggobject-and-ccompolyobject.md)  
 Обсуждается макросы **DECLARE\_\*\_AGGREGATABLE** влияют на использование `CComObject`, `CComAggObject` и `CComPolyObject`.  
  
 [Поддержка IDispatch и IErrorInfo](../atl/supporting-idispatch-and-ierrorinfo.md)  
 Приводит список классов реализации библиотеки ATL для поддержки интерфейсов `IDispatch` и **IErrorInfo**.  
  
 [Поддержка IDispEventImpl](../atl/supporting-idispeventimpl.md)  
 Рассматриваются шаги, чтобы реализовать точки подключения для класса.  
  
 [Изменить модель по умолчанию фабрики классов и агрегата](../atl/changing-the-default-class-factory-and-aggregation-model.md)  
 Показать, какие макросы, используемый для изменения по умолчанию используется фабрика класса и агрегат модель.  
  
 [Создание объединенный объект](../atl/creating-an-aggregated-object.md)  
 Содержит инструкции по созданию объединенный объект.  
  
## Связанные разделы  
 [Создание проекта библиотеки ATL](../atl/reference/creating-an-atl-project.md)  
 Содержит сведения о создании COM\-объект библиотеки ATL.  
  
 [Библиотека ATL](../atl/active-template-library-atl-concepts.md)  
 Содержит ссылки на концептуальные разделы о том, как запрограммировать с помощью библиотека шаблонных классов ATL.  
  
## См. также  
 [Основные понятия](../atl/active-template-library-atl-concepts.md)