---
title: Макросы реестра | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- atlcom/ATL::_ATL_STATIC_REGISTRY
- atlcom/ATL::DECLARE_LIBID
- atlcom/ATL::DECLARE_NO_REGISTRY
- atlcom/ATL::DECLARE_REGISTRY
- atlcom/ATL::DECLARE_REGISTRY_APPID_RESOURCEID
- atlcom/ATL::DECLARE_REGISTRY_RESOURCE
- atlcom/ATL::DECLARE_REGISTRY_RESOURCEID
dev_langs:
- C++
helpviewer_keywords:
- registry, ATL macros
ms.assetid: 3ee041da-c63b-42a4-89cf-2a4b2a6f81ae
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c10908454252b1ae381a2b96835ce09f3aa6db6f
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/25/2018
ms.locfileid: "50053660"
---
# <a name="registry-macros"></a>Макросы реестра

Эти макросы определяют полезный тип средства библиотеки и реестра.

|||
|-|-|
|[_ATL_STATIC_REGISTRY](#_atl_static_registry)|Указывает, что регистрационный код для объекта в объект во избежание зависимости от ATL. БИБЛИОТЕКА DLL.|
|[DECLARE_LIBID](#declare_libid)|Предоставляет способ для ATL для получения *libid* библиотеки типов.|
|[DECLARE_NO_REGISTRY](#declare_no_registry)|Позволяет избежать регистрации ATL по умолчанию.|
|[DECLARE_REGISTRY](#declare_registry)|Вводит или удаляет записи основного объекта в системном реестре.|
|[DECLARE_REGISTRY_APPID_RESOURCEID](#declare_registry_appid_resourceid)|Указывает сведения, необходимые для автоматической регистрации *appid*.|
|[DECLARE_REGISTRY_RESOURCE](#declare_registry_resource)|Именованный ресурс обнаружен и запускает его реестра внутри него.|
|[DECLARE_REGISTRY_RESOURCEID](#declare_registry_resourceid)|Находит ресурс, идентифицируемый идентификатор и запускает скрипт реестра, в ней.|

## <a name="requirements"></a>Требования

**Заголовок:** atlcom.h

##  <a name="_atl_static_registry"></a>  _ATL_STATIC_REGISTRY

Символ, указывающий, требуется регистрационный код для объекта в объект во избежание зависимости от ATL. БИБЛИОТЕКА DLL.

```
#define _ATL_STATIC_REGISTRY
```

### <a name="remarks"></a>Примечания

При определении ATL_STATIC_REGISTRY, следует использовать следующий код:

[!code-cpp[NVC_ATL_EventHandlingSample#5](../../atl/codesnippet/cpp/registry-macros_1.cpp)]

##  <a name="declare_libid"></a>  DECLARE_LIBID

Предоставляет способ для ATL для получения *libid* библиотеки типов.

```
DECLARE_LIBID( libid )
```

### <a name="parameters"></a>Параметры

*Идентификатор LIBID*<br/>
Идентификатор GUID библиотеки типов.

### <a name="remarks"></a>Примечания

Использовать DECLARE_LIBID в `CAtlModuleT`-производного класса.

### <a name="example"></a>Пример

Проекты ATL с атрибутами не созданный мастером будет иметь пример использования этого макроса.

##  <a name="declare_no_registry"></a>  DECLARE_NO_REGISTRY

Используйте DECLARE_NO_REGISTRY, если вы хотите избежать любой регистрации ATL по умолчанию для класса, в котором отображается этот макрос.

```
DECLARE_NO_REGISTRY()
```

##  <a name="declare_registry"></a>  DECLARE_REGISTRY

Вводит стандартный класс регистрации в системном реестре или удаляет его из системного реестра.

```
DECLARE_REGISTRY(
    class,
    pid,
    vpid,
    nid,
    flags )
```

### <a name="parameters"></a>Параметры

*class*<br/>
[in] Включен для обеспечения обратной совместимости.

*pid*<br/>
[in] LPCTSTR, который является идентификатором зависящий от версии программы.

*vpid*<br/>
[in] Значение LPCTSTR, являющийся идентификатором независящим от версии программы.

*nid*<br/>
[in] UINT, которое является индексом строки ресурса в реестре для использования в качестве описание программы.

*flags*<br/>
[in] DWORD, содержащее программы потоковой модели в реестре. Должен принимать одно из следующих значений: THREADFLAGS_APARTMENT, THREADFLAGS_BOTH или AUTPRXFLAG.

### <a name="remarks"></a>Примечания

Стандартный регистрации состоит из CLSID, идентификатор программы, идентификатор программы независимый от версий, строку описания и потоковую модель.

При создании объекта или элемента управления с помощью мастера добавления класса ATL, мастер автоматически реализует поддержку реестра на основе сценария и добавляет [DECLARE_REGISTRY_RESOURCEID](#declare_registry_resourceid) макрос к своим файлам. Если требуется поддержка реестра на основе сценария, необходимо заменить этот макрос DECLARE_REGISTRY. DECLARE_REGISTRY вставляет только пять основных ключей, описанных выше, в реестр. Необходимо вручную написать код, чтобы вставить другие ключи в реестр.

##  <a name="declare_registry_appid_resourceid"></a>  DECLARE_REGISTRY_APPID_RESOURCEID

Указывает сведения, необходимые для автоматической регистрации *appid*.

```
DECLARE_REGISTRY_APPID_RESOURCEID(
    resid,
    appid )
```

### <a name="parameters"></a>Параметры

*Идентификатор ресурса*<br/>
Идентификатор ресурса RGS-файл, содержащий сведения о *appid*.

*Идентификатор приложения*<br/>
Идентификатор GUID.

### <a name="remarks"></a>Примечания

Использовать DECLARE_REGISTRY_APPID_RESOURCEID в `CAtlModuleT`-производного класса.

### <a name="example"></a>Пример

Классы, которые добавлены в проекты ATL с помощью мастера добавления класса кода будут иметь пример использования этого макроса.

##  <a name="declare_registry_resource"></a>  DECLARE_REGISTRY_RESOURCE

Получает именованный ресурс, содержащий файл реестра и запускает его для ввода объектов в системном реестре или удалить их из системного реестра.

```
DECLARE_REGISTRY_RESOURCE( x )
```

### <a name="parameters"></a>Параметры

*x*<br/>
[in] Идентификатор ресурса строки.

### <a name="remarks"></a>Примечания

При создании объекта или элемента управления с помощью мастера проектов ATL, мастер автоматически реализовывать поддержку на основе сценария реестра и добавьте [DECLARE_REGISTRY_RESOURCEID](#declare_registry_resourceid) макросом, который аналогичен DECLARE_REGISTRY_ РЕСУРС, к файлам.

Кроме того, можно статически связать с компонент реестра ATL (регистратор) для доступа к реестру оптимизированный. Статически связывает на код регистратора, добавьте следующую строку в файле stdafx.h:

[!code-cpp[NVC_ATL_COM#56](../../atl/codesnippet/cpp/registry-macros_2.h)]

Если требуется ATL для замены значений для замены во время выполнения, не указывайте DECLARE_REGISTRY_RESOURCE или DECLARE_REGISTRY_RESOURCEID макрос. Вместо этого создайте массив `_ATL_REGMAP_ENTRIES` структуры, где каждая запись содержит переменной заполнитель в паре со значением для замены заполнителя во время выполнения. Затем вызовите [CAtlModule::UpdateRegistryFromResourceD](catlmodule-class.md#updateregistryfromresourced) или [CAtlModule::UpdateRegistryFromResourceS](catlmodule-class.md#updateregistryfromresources), передавая массив. Это добавляет все значения замены в `_ATL_REGMAP_ENTRIES` структур карту замены регистратора.

Дополнительные сведения о подстановочных параметров и сценариев см. в статье [компонент реестра ATL (регистратор)](../../atl/atl-registry-component-registrar.md).

##  <a name="declare_registry_resourceid"></a>  DECLARE_REGISTRY_RESOURCEID

Совпадение с кодом [DECLARE_REGISTRY_RESOURCE](#declare_registry_resource) за исключением того, что создаваемые мастером целое число без знака используются для идентификации ресурса, а не имя строки.

```
DECLARE_REGISTRY_RESOURCEID( x )
```

### <a name="parameters"></a>Параметры

*x*<br/>
[in] Создаваемые мастером идентификатор ресурса.

### <a name="remarks"></a>Примечания

При создании объекта или элемента управления с помощью мастера проектов ATL, мастер автоматически реализовывать поддержку на основе сценария реестра и добавить макрос DECLARE_REGISTRY_RESOURCEID в файлы.

Кроме того, можно статически связать с компонент реестра ATL (регистратор) для доступа к реестру оптимизированный. Статически связывает на код регистратора, добавьте следующую строку в файле stdafx.h:

[!code-cpp[NVC_ATL_COM#56](../../atl/codesnippet/cpp/registry-macros_2.h)]

Если требуется ATL для замены значений для замены во время выполнения, не указывайте DECLARE_REGISTRY_RESOURCE или DECLARE_REGISTRY_RESOURCEID макрос. Вместо этого создайте массив `_ATL_REGMAP_ENTRIES` структуры, где каждая запись содержит переменной заполнитель в паре со значением для замены заполнителя во время выполнения. Затем вызовите [CAtlModule::UpdateRegistryFromResourceD](catlmodule-class.md#updateregistryfromresourced) или [CAtlModule::UpdateRegistryFromResourceS](catlmodule-class.md#updateregistryfromresources), передавая массив. Это добавляет все значения замены в `_ATL_REGMAP_ENTRIES` структур карту замены регистратора.

Дополнительные сведения о подстановочных параметров и сценариев см. в статье [компонент реестра ATL (регистратор)](../../atl/atl-registry-component-registrar.md).

## <a name="see-also"></a>См. также

[Макросы](../../atl/reference/atl-macros.md)
