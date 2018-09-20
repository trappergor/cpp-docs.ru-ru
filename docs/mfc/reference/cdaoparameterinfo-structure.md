---
title: Структура CDaoParameterInfo | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CDaoParameterInfo
dev_langs:
- C++
helpviewer_keywords:
- CDaoParameterInfo structure [MFC]
- DAO (Data Access Objects), Parameters collection
ms.assetid: 45fd53cd-cb84-4e12-b48d-7f2979f898ad
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 8f695d1873a2a5a29393da347567674bf1f08e01
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46433261"
---
# <a name="cdaoparameterinfo-structure"></a>Структура CDaoParameterInfo

`CDaoParameterInfo` Структура содержит сведения об объекте параметров, определенных для объектах доступа к данным (DAO).

## <a name="syntax"></a>Синтаксис

```
struct CDaoParameterInfo
{
    CString m_strName;       // Primary
    short m_nType;           // Primary
    ColeVariant m_varValue;  // Secondary
};
```

#### <a name="parameters"></a>Параметры

*m_strName*<br/>
Однозначно называет объект параметра. Дополнительные сведения см. в разделе «Имя свойства» в справке DAO.

*m_nType*<br/>
Значение, указывающее тип данных объекта parameter. Список возможных значений, см. в разделе *m_nType* членом [CDaoFieldInfo](../../mfc/reference/cdaofieldinfo-structure.md) структуры. Дополнительные сведения см. в разделе «Тип свойства» в справке DAO.

*m_varValue*<br/>
Значение параметра, хранящиеся в [COleVariant](../../mfc/reference/colevariant-class.md) объекта.

## <a name="remarks"></a>Примечания

Ссылки на первичной и вторичной выше указывают, как возвращаются данные по [GetParameterInfo](../../mfc/reference/cdaoquerydef-class.md#getparameterinfo) функции-члена в классе `CDaoQueryDef`.

MFC не инкапсулировать объекты параметров DAO в классе. MFC базовых объектов DAO querydef `CDaoQueryDef` объекты хранят параметры в своих коллекциях параметров. Для доступа к объектам параметра в [CDaoQueryDef](../../mfc/reference/cdaoquerydef-class.md) , вызовите объекта querydef `GetParameterInfo` функция-член для определенного параметра имя или индекс в коллекции параметров. Можно использовать [CDaoQueryDef::GetParameterCount](../../mfc/reference/cdaoquerydef-class.md#getparametercount) функция-член в сочетании с `GetParameterInfo` циклический перебор коллекции параметров.

Сведений, получаемых методом [CDaoQueryDef::GetParameterInfo](../../mfc/reference/cdaoquerydef-class.md#getparameterinfo) функция-член хранится в `CDaoParameterInfo` структуры. Вызовите `GetParameterInfo` для объекта querydef, в которых коллекции параметров хранится объект параметра.

> [!NOTE]
>  Если вы хотите получить или задать только значение параметра, используйте [GetParamValue](../../mfc/reference/cdaorecordset-class.md#getparamvalue) и [SetParamValue](../../mfc/reference/cdaorecordset-class.md#setparamvalue) функции-члены класса `CDaoRecordset`.

`CDaoParameterInfo` также определяет `Dump` создает функцию-член в режиме отладки. Можно использовать `Dump` для помещения в дамп содержимое `CDaoParameterInfo` объекта.

## <a name="requirements"></a>Требования

**Заголовок:** afxdao.h

## <a name="see-also"></a>См. также

[Структуры, стили, обратные вызовы и схемы сообщений](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)<br/>
[Класс CDaoQueryDef](../../mfc/reference/cdaoquerydef-class.md)
