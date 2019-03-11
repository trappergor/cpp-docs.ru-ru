---
title: Пространство имен Platform::Metadata
ms.date: 12/30/2016
ms.topic: reference
f1_keywords:
- VCCORLIB/Platform::Metadata
helpviewer_keywords:
- Platform::Metadata Namespace
ms.assetid: e3e114d8-a4b0-47f0-865a-9ce9d7212e86
ms.openlocfilehash: 9626b3a9d28d28fd52a0d2295af8fda8855cd90c
ms.sourcegitcommit: dedd4c3cb28adec3793329018b9163ffddf890a4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/11/2019
ms.locfileid: "57739452"
---
# <a name="platformmetadata-namespace"></a>Пространство имен Platform::Metadata

Это пространство имен содержит атрибуты, которые изменяют объявления типов.

## <a name="syntax"></a>Синтаксис

```cpp
namespace Platform {
   namespace Metadata {
}}
```

### <a name="members"></a>Участники

Хотя это пространство имен предназначено для внутреннего использования, следующие его члены могут отображаться в браузерах.

|name|Примечание|
|----------|------------|
|Атрибут|Базовый класс для атрибутов.|
|[Атрибут Platform::Metadata::DefaultMemberAttribute](../cppcx/platform-metadata-defaultmemberattribute-attribute.md)|Указывает предпочтительную вызываемую функцию из нескольких возможных перегруженных функций.|
|[Атрибут Platform::Metadata::FlagsAttribute](../cppcx/platform-metadata-flagsattribute-attribute.md)|Объявляет перечисление как перечисление битовых полей.<br /><br /> В следующем примере показано применение атрибута `Flags` к перечислению.<br /><br /> `[Flags] enum class MyEnumeration { enumA = 1, enumB = 2, enumC = 3}`|
|[Platform::Metadata::RuntimeClassNameAttribute](../cppcx/platform-metadata-runtimeclassname.md)|Проверяет, что закрытому классу ссылки присвоено допустимое имя класса среды выполнения.|

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`Platform`

### <a name="requirements"></a>Требования

**Метаданные:** platform.winmd

**Пространство имен:** Platform::Metadata

## <a name="see-also"></a>См. также

[Пространство имен Platform](platform-namespace-c-cx.md)
