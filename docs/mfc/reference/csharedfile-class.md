---
title: Класс CSharedFile
ms.date: 11/04/2016
f1_keywords:
- CSharedFile
- AFXADV/CSharedFile
- AFXADV/CSharedFile::CSharedFile
- AFXADV/CSharedFile::Detach
- AFXADV/CSharedFile::SetHandle
helpviewer_keywords:
- CSharedFile [MFC], CSharedFile
- CSharedFile [MFC], Detach
- CSharedFile [MFC], SetHandle
ms.assetid: 5d000422-9ede-4318-a8c9-f7412b674f39
ms.openlocfilehash: 0a9bbf3072a665c04501025d421839fa90a37225
ms.sourcegitcommit: 6cf0c67acce633b07ff31b56cebd5de3218fd733
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/24/2019
ms.locfileid: "67344424"
---
# <a name="csharedfile-class"></a>Класс CSharedFile

[CMemFile](../../mfc/reference/cmemfile-class.md)-производный класс, который поддерживает общие файлы памяти.

## <a name="syntax"></a>Синтаксис

```
class CSharedFile : public CMemFile
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|name|Описание|
|----------|-----------------|
|[CSharedFile::CSharedFile](#csharedfile)|Создает объект `CSharedFile`.|

### <a name="public-methods"></a>Открытые методы

|name|Описание|
|----------|-----------------|
|[CSharedFile::Detach](#detach)|Закрывает файл общей памяти и возвращает дескриптор блока памяти.|
|[CSharedFile::SetHandle](#sethandle)|Вложения файла в общей памяти блок памяти.|

## <a name="remarks"></a>Примечания

Файлы в памяти, ведут себя как файлы на диске. Разница, файл памяти хранятся в оперативной памяти, а не на диске. Файл памяти полезно для обеспечивается быстродействие временного хранилища, или для передачи необработанные байты или сериализованных объектов между независимые процессы.

Файлы общей памяти отличаются от других файлов в памяти, что память для них выделяется с помощью [GlobalAlloc](/windows/desktop/api/winbase/nf-winbase-globalalloc) функции Windows. `CSharedFile` Класс хранит данные в глобально выделенного блока памяти (созданные с помощью `GlobalAlloc`), и этот блок памяти может совместно с помощью DDE, буфер обмена или других OLE/COM универсальный операций передачи данных, например, с помощью `IDataObject`.

`GlobalAlloc` Возвращает HGLOBAL обработки, а не указатель на буфер, такие как указатель, возвращенный [malloc](../../c-runtime-library/reference/malloc.md). Дескриптор HGLOBAL необходима в некоторых приложениях. Например чтобы поместить данные в буфере обмена необходимо дескриптор HGLOBAL.

`CSharedFile` не использовать файлы, отображенные в память, а данные не предоставляется напрямую между процессами.

`CSharedFile` объекты можно автоматически назначать собственной памятью. Или можно присоединить собственный блок памяти, который `CSharedFile` путем вызова метода [CSharedFile::SetHandle](#sethandle). В любом случае память для растущих файле памяти автоматически выделяется `nGrowBytes`-размера с шагом, если `nGrowBytes` не равно нулю.

Дополнительные сведения см. в статье [файлы в MFC](../../mfc/files-in-mfc.md) и [обработка файлов](../../c-runtime-library/file-handling.md) в *Справочник по библиотеке времени выполнения*.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CFile](../../mfc/reference/cfile-class.md)

[CMemFile](../../mfc/reference/cmemfile-class.md)

`CSharedFile`

## <a name="requirements"></a>Требования

**Заголовок:** afxadv.h

##  <a name="csharedfile"></a>  CSharedFile::CSharedFile

Создает `CSharedFile` объекта и выделяет память для него.

```
CSharedFile(
    UINT nAllocFlags = GMEM_DDESHARE | GMEM_MOVEABLE,
    UINT nGrowBytes = 4096);
```

### <a name="parameters"></a>Параметры

*nAllocFlags*<br/>
Флаги, указывающие, как память будет выделяться. См. в разделе [GlobalAlloc](/windows/desktop/api/winbase/nf-winbase-globalalloc) список допустимых значений флагов.

*nGrowBytes*<br/>
Приращение выделения памяти в байтах.

##  <a name="detach"></a>  CSharedFile::Detach

Вызывайте эту функцию, чтобы закрыть файл памяти и отсоединить его от блока памяти.

```
HGLOBAL Detach();
```

### <a name="return-value"></a>Возвращаемое значение

Дескриптор блока памяти, который содержит содержимое файла памяти.

### <a name="remarks"></a>Примечания

Вы можете повторно открыть его, вызвав [метод](#sethandle), используя дескриптор, возвращенный **отсоединения**.

##  <a name="sethandle"></a>  CSharedFile::SetHandle

Вызывайте эту функцию для присоединения блок глобальную память для `CSharedFile` объекта.

```
void SetHandle(
    HGLOBAL hGlobalMemory,
    BOOL bAllowGrow = TRUE);
```

### <a name="parameters"></a>Параметры

*hGlobalMemory*<br/>
Дескриптор к глобальной памяти должны быть присоединены к `CSharedFile`.

*bAllowGrow*<br/>
Указывает, может ли увеличиваться блок памяти.

### <a name="remarks"></a>Примечания

Если *bAllowGrow* имеет ненулевое значение, размер блока памяти увеличивается при необходимости, например, при попытке записать большее число байтов в файл, чем размер блока памяти.

## <a name="see-also"></a>См. также

[Класс CMemFile](../../mfc/reference/cmemfile-class.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Класс CMemFile](../../mfc/reference/cmemfile-class.md)
