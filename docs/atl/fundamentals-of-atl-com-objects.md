---
title: Основы объектов ATL COM
ms.date: 11/19/2018
helpviewer_keywords:
- COM, and ATL
- ATL, COM
- ATL COM objects
- COM objects, ATL
ms.assetid: 0f9c9d98-cc28-45da-89ac-dc94cee422fe
ms.openlocfilehash: 651413534ed44143e2a0fdaf00bdabd6e5d57010
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81319560"
---
# <a name="fundamentals-of-atl-com-objects"></a>Основы объектов ATL COM

На следующей иллюстрации показана взаимосвязь между классами и интерфейсами, которые используются для определения объекта ATL COM.

![Структура ATL](../atl/media/vc307y1.gif "Структура ATL")

> [!NOTE]
> На этой `CComObject` диаграмме показано, что происходит от `CYourClass` того, что `CComAggObject` и `CComPolyObject` включают `CYourClass` в качестве переменной члена.

Существует три способа определения объекта ATL COM. Стандартным вариантом является `CComObject` использование класса, `CYourClass`который является производным от . Второй вариант заключается в создании агрегированного объекта с помощью `CComAggObject` класса. Третий вариант заключается `CComPolyObject` в использовании класса. `CComPolyObject`действует как гибрид: он может `CComObject` функционировать `CComAggObject` как класс или как класс, в зависимости от того, как он впервые создан. Для получения дополнительной информации `CComPolyObject` о том, как использовать класс, см. [CComPolyObject Class](../atl/reference/ccompolyobject-class.md)

При использовании стандартного ATL COM используются два объекта: внешний объект и внутренний объект. Внешние клиенты получают доступ к функциональности внутреннего объекта через функции обертки, которые определяются во внешнем объекте. Внешний объект имеет `CComObject`тип.

При использовании агрегированного объекта внешний объект не предоставляет обертки для функциональности внутреннего объекта. Вместо этого внешний объект предоставляет указатель, который непосредственно доступен внешним клиентам. В этом сценарии внешний `CComAggObject`объект имеет тип. Внутренний объект является переменной члена внешнего объекта, `CYourClass`и он имеет тип.

Поскольку клиенту не нужно проходить через внешний объект для взаимодействия с внутренним объектом, агрегированные объекты, как правило, более эффективны. Кроме того, внешний объект не должен знать функциональность агрегированного объекта, учитывая, что интерфейс агрегированного объекта напрямую доступен клиенту. Однако не все объекты могут быть агрегированы. Для агрегирования объекта он должен быть разработан с учетом агрегации.

ATL реализует [IUnknown](/windows/win32/api/unknwn/nn-unknwn-iunknown) в два этапа:

- [CComObject](../atl/reference/ccomobject-class.md), [CComAggObject](../atl/reference/ccomaggobject-class.md), или [CComPolyObject](../atl/reference/ccompolyobject-class.md) реализует `IUnknown` методы.

- [CComObjectRoot](../atl/reference/ccomobjectroot-class.md) или [CComObjectRootEx](../atl/reference/ccomobjectrootex-class.md) управляет эталоном и `IUnknown`внешними указателями.

Другие аспекты объекта ATL COM обрабатываются другими классами:

- [CComCoClass](../atl/reference/ccomcoclass-class.md) определяет фабрику и модель агрегации класса по умолчанию объекта.

- [IDispatchImpl](../atl/reference/idispatchimpl-class.md) обеспечивает реализацию `IDispatch Interface` по умолчанию части любых двойных интерфейсов на объекте.

- [ISupportErrorInfoImpl](../atl/reference/isupporterrorinfoimpl-class.md) реализует `ISupportErrorInfo` интерфейс, который гарантирует, что информация об ошибках может быть распространена в цепочке вызовов правильно.

## <a name="in-this-section"></a>в этом разделе

[Реализация CComObjectRootEx](../atl/implementing-ccomobjectrootex.md)<br/>
Отображение примера `CComObjectRootEx`записей карты COM для реализации.

[Реализация CComObject, CComAggObject и CComPolyObject](../atl/implementing-ccomobject-ccomaggobject-and-ccompolyobject.md)<br/>
Обсуждает, как **\*DECLARE_ _AGGREGATABLE** макросы `CComObject` `CComAggObject`влияют `CComPolyObject`на использование , и .

[Поддержка IDispatch и IErrorInfo](../atl/supporting-idispatch-and-ierrorinfo.md)<br/>
Перечисляет классы реализации ATL `IDispatch` для `IErrorInfo` поддержки интерфейсов и интерфейсов.

[Поддержка IDispEventImpl](../atl/supporting-idispeventimpl.md)<br/>
Обсуждается шаги по реализации точки соединения для вашего класса.

[Изменение модели класса по умолчанию и модели агрегирования](../atl/changing-the-default-class-factory-and-aggregation-model.md)<br/>
Покажите, какие макросы использовать для изменения модели класса по умолчанию и модели агрегирования.

[Создание агрегированного объекта](../atl/creating-an-aggregated-object.md)<br/>
Перечисляет шаги для создания агрегированного объекта.

## <a name="related-sections"></a>Связанные разделы

[Создание проекта ATL](../atl/reference/creating-an-atl-project.md)<br/>
Предоставляет информацию о создании объекта ATL COM.

[ATL](../atl/active-template-library-atl-concepts.md)<br/>
Ссылки на разделы о программировании с использованием библиотеки ATL.

## <a name="see-also"></a>См. также раздел

[Основные понятия](../atl/active-template-library-atl-concepts.md)
