---
title: Реестр Макрос
ms.date: 08/19/2019
f1_keywords:
- atlcom/ATL::_ATL_STATIC_REGISTRY
- atlcom/ATL::DECLARE_LIBID
- atlcom/ATL::DECLARE_NO_REGISTRY
- atlcom/ATL::DECLARE_REGISTRY
- atlcom/ATL::DECLARE_REGISTRY_APPID_RESOURCEID
- atlcom/ATL::DECLARE_REGISTRY_RESOURCE
- atlcom/ATL::DECLARE_REGISTRY_RESOURCEID
helpviewer_keywords:
- registry, ATL macros
ms.assetid: 3ee041da-c63b-42a4-89cf-2a4b2a6f81ae
ms.openlocfilehash: fd012b4300f4cd72cdc9ab363b770ac1dbefa06e
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81326043"
---
# <a name="registry-macros"></a>Реестр Макрос

Эти макросы определяют полезные типы библиотек и реестробъектов.

|||
|-|-|
|[_ATL_STATIC_REGISTRY](#_atl_static_registry)|Означает, что необходимо, чтобы код регистрации объекта находился в объекте, чтобы избежать зависимости от ATL. Dll.|
|[DECLARE_LIBID](#declare_libid)|Предоставляет возможность для ATL получить *libid* библиотеки типа.|
|[DECLARE_NO_REGISTRY](#declare_no_registry)|Избегает регистрации ATL по умолчанию.|
|[DECLARE_REGISTRY](#declare_registry)|Вводит или удаляет запись основного объекта в системном реестре.|
|[DECLARE_REGISTRY_APPID_RESOURCEID](#declare_registry_appid_resourceid)|Определяет информацию, необходимую для автоматической регистрации *приложения.*|
|[DECLARE_REGISTRY_RESOURCE](#declare_registry_resource)|Находит названный ресурс и запускает в нем скрипт реестра.|
|[DECLARE_REGISTRY_RESOURCEID](#declare_registry_resourceid)|Находит ресурс, идентифицированный идентификационным номером, и запускает в нем скрипт реестра.|

## <a name="requirements"></a>Требования

**Заголовок:** atlcom.h

## <a name="_atl_static_registry"></a><a name="_atl_static_registry"></a>_ATL_STATIC_REGISTRY

Символ, указывающий на то, что код регистрации объекта должен находиться в объекте, чтобы избежать зависимости от ATL. Dll.

```
#define _ATL_STATIC_REGISTRY
```

### <a name="remarks"></a>Remarks

При определении ATL_STATIC_REGISTRY следует использовать следующий код:

[!code-cpp[NVC_ATL_EventHandlingSample#5](../../atl/codesnippet/cpp/registry-macros_1.cpp)]

## <a name="declare_libid"></a><a name="declare_libid"></a>DECLARE_LIBID

Предоставляет возможность для ATL получить *libid* библиотеки типа.

```
DECLARE_LIBID( libid )
```

### <a name="parameters"></a>Параметры

*Libid*<br/>
Идентификатор GUID библиотеки типов.

### <a name="remarks"></a>Remarks

Используйте DECLARE_LIBID `CAtlModuleT`в классе, полученном.

### <a name="example"></a>Пример

Неприписываемые мастер-генерируемые проекты ATL будут иметь образец использования этого макроса.

## <a name="declare_no_registry"></a><a name="declare_no_registry"></a>DECLARE_NO_REGISTRY

Используйте DECLARE_NO_REGISTRY, если вы хотите избежать регистрации ATL по умолчанию для класса, в котором отображается этот макрос.

```
DECLARE_NO_REGISTRY()
```

## <a name="declare_registry"></a><a name="declare_registry"></a>DECLARE_REGISTRY

Вводит регистрацию стандартного класса в системный реестр или удаляет его из системного реестра.

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
(в) Включено для обратной совместимости.

*Pid*<br/>
(в) LPCTSTR, который является идентификатором программы для конкретной версии.

*vpid*<br/>
(в) LPCTSTR, который является идентификатором программы, не зависимым от версий.

*Nid*<br/>
(в) UINT, который является индексом строки ресурса в реестре для использования в качестве описания программы.

*Флаги*<br/>
(в) DWORD, содержащий модель потоков программы в реестре. Должно быть одно из следующих значений: THREADFLAGS_APARTMENT, THREADFLAGS_BOTH или AUTPRXFLAG.

### <a name="remarks"></a>Remarks

Стандартная регистрация состоит из CLSID, идентификатора программы, идентификатора независимой версии программы, строки описания и модели потока.

При создании объекта или элементе управления с помощью atL Add Class Wizard мастер автоматически реализует поддержку реестра на основе сценариев и добавляет [DECLARE_REGISTRY_RESOURCEID](#declare_registry_resourceid) макрос в файлы. Если вы не хотите поддержки реестра на основе сценариев, вам необходимо заменить этот макрос DECLARE_REGISTRY. DECLARE_REGISTRY вставляет в реестр только пять основных ключей, описанных выше. Вы должны вручную написать код, чтобы вставить другие ключи в реестр.

## <a name="declare_registry_appid_resourceid"></a><a name="declare_registry_appid_resourceid"></a>DECLARE_REGISTRY_APPID_RESOURCEID

Определяет информацию, необходимую для автоматической регистрации *приложения.*

```
DECLARE_REGISTRY_APPID_RESOURCEID(
    resid,
    appid )
```

### <a name="parameters"></a>Параметры

*Resid*<br/>
Идентификатор ресурса файла .rgs, содержащего информацию об *аппидо.*

*Appid*<br/>
Идентификатор GUID.

### <a name="remarks"></a>Remarks

Используйте DECLARE_REGISTRY_APPID_RESOURCEID `CAtlModuleT`в классе - производные.

### <a name="example"></a>Пример

Классы, добавленные в проекты ATL с мастером кода Add Class, будут иметь образец использования этого макроса.

## <a name="declare_registry_resource"></a><a name="declare_registry_resource"></a>DECLARE_REGISTRY_RESOURCE

Получает названный ресурс, содержащий файл реестра, и запускает скрипт, чтобы либо ввести объекты в системный реестр, либо удалить их из системного реестра.

```
DECLARE_REGISTRY_RESOURCE( x )
```

### <a name="parameters"></a>Параметры

*x*<br/>
(в) Строка идентификатор вашего ресурса.

### <a name="remarks"></a>Remarks

При создании объекта или управления с помощью ATL Project Wizard мастер автоматически реализует поддержку реестра на основе скрипта и добавляет в файлы [DECLARE_REGISTRY_RESOURCEID](#declare_registry_resourceid) макрос, похожий на DECLARE_REGISTRY_RESOURCE.

Вы можете статически связать с компонентом реестра ATL (регистратор) для оптимизированного доступа к реестру. Чтобы статически связаться с кодом Регистратора, добавьте следующую строку в файл *pch.h* *(stdafx.h* в Visual Studio 2017 и более раньше):

[!code-cpp[NVC_ATL_COM#56](../../atl/codesnippet/cpp/registry-macros_2.h)]

Если вы хотите, чтобы ATL заменил значения замены во время выполнения, не укажите DECLARE_REGISTRY_RESOURCE или DECLARE_REGISTRY_RESOURCEID макрос. Вместо этого создайте `_ATL_REGMAP_ENTRIES` массив структур, где каждая запись содержит переменный заполнитель в паре со значением для замены заполнителя во время выполнения. Затем позвоните [cAtlModule::UpdateRegistryFromResourceD](catlmodule-class.md#updateregistryfromresourced) или [CAtlModule::UpdateRegistryFromResourceS](catlmodule-class.md#updateregistryfromresources), проходя массив. Это добавляет все значения замены `_ATL_REGMAP_ENTRIES` в структурах на карту замены Регистратора.

Для получения дополнительной информации о сменных параметров и сценариев, [см.](../../atl/atl-registry-component-registrar.md)

## <a name="declare_registry_resourceid"></a><a name="declare_registry_resourceid"></a>DECLARE_REGISTRY_RESOURCEID

Так же, как [DECLARE_REGISTRY_RESOURCE,](#declare_registry_resource) за исключением того, что он использует мастер-генерируемых UINT для идентификации ресурса, а не строки имя.

```
DECLARE_REGISTRY_RESOURCEID( x )
```

### <a name="parameters"></a>Параметры

*x*<br/>
(в) Идентификатор вашего ресурса, генерируемый мастером.

### <a name="remarks"></a>Remarks

При создании объекта или управления с помощью ATL Project Wizard мастер автоматически реализует поддержку реестра на основе скрипта и добавляет DECLARE_REGISTRY_RESOURCEID макрос в файлы.

Вы можете статически связать с компонентом реестра ATL (регистратор) для оптимизированного доступа к реестру. Чтобы статически связаться с кодом Регистратора, добавьте следующую строку в файл *stdafx.h* *(pch.h* в Visual Studio 2019 и позже):

[!code-cpp[NVC_ATL_COM#56](../../atl/codesnippet/cpp/registry-macros_2.h)]

Если вы хотите, чтобы ATL заменил значения замены во время выполнения, не укажите DECLARE_REGISTRY_RESOURCE или DECLARE_REGISTRY_RESOURCEID макрос. Вместо этого создайте `_ATL_REGMAP_ENTRIES` массив структур, где каждая запись содержит переменный заполнитель в паре со значением для замены заполнителя во время выполнения. Затем позвоните [cAtlModule::UpdateRegistryFromResourceD](catlmodule-class.md#updateregistryfromresourced) или [CAtlModule::UpdateRegistryFromResourceS](catlmodule-class.md#updateregistryfromresources), проходя массив. Это добавляет все значения замены `_ATL_REGMAP_ENTRIES` в структурах на карту замены Регистратора.

Для получения дополнительной информации о сменных параметров и сценариев, [см.](../../atl/atl-registry-component-registrar.md)

## <a name="see-also"></a>См. также раздел

[Макросы](../../atl/reference/atl-macros.md)
