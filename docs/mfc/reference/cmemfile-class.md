---
title: Класс CMemFile
ms.date: 11/04/2016
f1_keywords:
- CMemFile
- AFX/CMemFile
- AFX/CMemFile::CMemFile
- AFX/CMemFile::Attach
- AFX/CMemFile::Detach
- AFX/CMemFile::Alloc
- AFX/CMemFile::Free
- AFX/CMemFile::GrowFile
- AFX/CMemFile::Memcpy
- AFX/CMemFile::Realloc
helpviewer_keywords:
- CMemFile [MFC], CMemFile
- CMemFile [MFC], Attach
- CMemFile [MFC], Detach
- CMemFile [MFC], Alloc
- CMemFile [MFC], Free
- CMemFile [MFC], GrowFile
- CMemFile [MFC], Memcpy
- CMemFile [MFC], Realloc
ms.assetid: 20e86515-e465-4f73-b2ea-e49789d63165
ms.openlocfilehash: 1bd88ad17bdb047de4c344ab96f3d9aecbe23c31
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2020
ms.locfileid: "81752635"
---
# <a name="cmemfile-class"></a>Класс CMemFile

[Класс CFile-](../../mfc/reference/cfile-class.md)производный, который поддерживает файлы памяти.

## <a name="syntax"></a>Синтаксис

```
class CMemFile : public CFile
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CMemFile::CMemFile](#cmemfile)|Строит объект файла памяти.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CMemFile::Прикрепите](#attach)|Прикрепляет блок памяти к `CMemFile`.|
|[CMemFile::Detach](#detach)|Отсоединяет блок памяти от `CMemFile` и возвращает указатель к блоку памяти отдельно.|

### <a name="protected-methods"></a>Защищенные методы

|Имя|Описание|
|----------|-----------------|
|[CMemFile::Alloc](#alloc)|Переопределить для изменения поведения распределения памяти.|
|[CMemFile::Бесплатно](#free)|Переопределение для изменения поведения срабатывая схожей памяти.|
|[CMemFile::GrowFile](#growfile)|Переопределить для изменения поведения при выращивании файла.|
|[CMemFile::Memcpy](#memcpy)|Переутомить для изменения поведения копии памяти при чтении и написании файлов.|
|[CMemFile::Realloc](#realloc)|Переопределение для изменения поведения перераспределения памяти.|

## <a name="remarks"></a>Remarks

Эти файлы памяти ведут себя как дисковые файлы, за исключением того, что файл хранится в оперативной памяти, а не на диске. Файл памяти полезен для быстрого временного хранения или для передачи необработанных байтов или сериализованных объектов между независимыми процессами.

`CMemFile`объекты могут автоматически выделять свою собственную память или `CMemFile` вы можете прикрепить свой собственный блок памяти к объекту, позвонив [в Атташ.](#attach) В любом случае память для получения файла `nGrowBytes`памяти автоматически выделяется в приращениях размера, если `nGrowBytes` она не равна нулю.

Блок памяти автоматически удаляется после `CMemFile` уничтожения объекта, если память `CMemFile` была первоначально выделена объектом; в противном случае вы несете ответственность за распределение памяти, присоединенной к объекту.

Вы можете получить доступ к блоку памяти через указатель, поставляемый при отсоединить его от `CMemFile` объекта, позвонив в [Detach.](#detach)

Наиболее `CMemFile` распространенным использованием `CMemFile` является создание объекта и использовать его, вызывая функции члена [CFile.](../../mfc/reference/cfile-class.md) Обратите внимание, `CMemFile` что создание автоматически открывает его: вы не вызываете [CFile::Open](../../mfc/reference/cfile-class.md#open), который используется только для дисковых файлов. Поскольку `CMemFile` дисковый файл не используется, `CFile::m_hFile` участник данных не используется.

Функции `CFile` участника [Duplicate,](../../mfc/reference/cfile-class.md#duplicate) [LockRange](../../mfc/reference/cfile-class.md#lockrange)и [UnlockRange](../../mfc/reference/cfile-class.md#unlockrange) не реализованы для. `CMemFile` Если вы называете `CMemFile` эти функции на объекте, вы получите [CNotSupportedException](../../mfc/reference/cnotsupportedexception-class.md).

`CMemFile`использует функции библиотеки времени выполнения [malloc,](../../c-runtime-library/reference/malloc.md) [realloc,](../../c-runtime-library/reference/realloc.md)и [свободно](../../c-runtime-library/reference/free.md) распределять, перераспределять, и deallocate память; и внутреннее [memcpy](../../c-runtime-library/reference/memcpy-wmemcpy.md) блокировать копию памяти при чтении и письме. Если вы хотите изменить это поведение или `CMemFile` поведение при росте файла, получите свой собственный класс из `CMemFile` соответствующих функций и переиздайте их.

Для получения `CMemFile`дополнительной информации о , см. [статьи Файлы в MFC](../../mfc/files-in-mfc.md) и [управления памятью (MFC)](../../mfc/memory-management.md) и см. [Обработка файлов](../../c-runtime-library/file-handling.md) в *Run-Time Библиотека Справка*.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CFile](../../mfc/reference/cfile-class.md)

`CMemFile`

## <a name="requirements"></a>Требования

**Заголовок:** afx.h

## <a name="cmemfilealloc"></a><a name="alloc"></a>CMemFile::Alloc

Эта функция вызывается функциями-членами. `CMemFile`

```
virtual BYTE* Alloc(SIZE_T nBytes);
```

### <a name="parameters"></a>Параметры

*nБайт*<br/>
Количество байтов памяти, которые будут распределены.

### <a name="return-value"></a>Возвращаемое значение

Указатель на блок памяти, который был выделен, или NULL, если выделение не удалось.

### <a name="remarks"></a>Remarks

Переопределить эту функцию для реализации пользовательского распределения памяти. Если вы переопределить эту функцию, вы, вероятно, хотите, чтобы переопределить [бесплатно](#free) и [Realloc,](#realloc) а также.

Реализация по умолчанию использует [функцию](../../c-runtime-library/reference/malloc.md) функции библиотеки времени выполнения для выделения памяти.

## <a name="cmemfileattach"></a><a name="attach"></a>CMemFile::Прикрепите

Вызов иэту функцию, чтобы `CMemFile`прикрепить блок памяти.

```cpp
void Attach(
    BYTE* lpBuffer,
    UINT nBufferSize,
    UINT nGrowBytes = 0);
```

### <a name="parameters"></a>Параметры

*lpBuffer*<br/>
Указатель на буфер, который `CMemFile`должен быть прикреплен к .

*nBufferSize*<br/>
Масштаб, который определяет размер буфера в байтах.

*nGrowBytes*<br/>
Распределение памяти в байтах.

### <a name="remarks"></a>Remarks

Это `CMemFile` приводит к использованию блока памяти в качестве файла памяти.

Если *nGrowBytes* 0, `CMemFile` установит длину файла *nBufferSize.* Это означает, что данные в блоке `CMemFile` памяти до его присоединения будут использоваться в качестве файла. Файлы памяти, созданные таким образом, не могут быть выращены.

Поскольку файл не может быть выращен, будьте осторожны, чтобы не вызвать `CMemFile` попытку вырастить файл. Например, не вызывайте `CMemFile` переопределения [CFile:Write,](../../mfc/reference/cfile-class.md#write) чтобы написать мимо конца или не вызывайте [CFile:SetLength](../../mfc/reference/cfile-class.md#setlength) с длиной длиннее *nBufferSize.*

Если *nGrowBytes* больше 0, `CMemFile` будет игнорировать содержимое блока памяти вы прилагали. Вам придется написать содержимое файла памяти `CMemFile` с `CFile::Write`нуля, используя переопределение . Если вы попытаетесь написать мимо конца файла `CMemFile` или вырастить файл, позвонив `CFile::SetLength`переопределение, `CMemFile` будет расти распределение памяти с шагом *nGrowBytes*. Выращивание выделения памяти не удастся, если блок памяти, который вы передаёте, `Attach` не был выделен методом, совместимым с [Alloc.](#alloc) Чтобы быть совместимым с `Alloc`реализацией по умолчанию, необходимо выделить память с функцией запуска библиотеки [malloc](../../c-runtime-library/reference/malloc.md) или [calloc.](../../c-runtime-library/reference/calloc.md)

## <a name="cmemfilecmemfile"></a><a name="cmemfile"></a>CMemFile::CMemFile

Первая перегрузка открывает пустой файл памяти.

```
CMemFile(UINT nGrowBytes = 1024);

CMemFile(
    BYTE* lpBuffer,
    UINT nBufferSize,
    UINT nGrowBytes = 0);
```

### <a name="parameters"></a>Параметры

*nGrowBytes*<br/>
Распределение памяти в байтах.

*lpBuffe*r Pointer в буфер, который получает информацию о размере *nBufferSize.*

*nBufferSize*<br/>
Масштаб, опосредуемый размер буфера файла, в байтах.

### <a name="remarks"></a>Remarks

Обратите внимание, что файл открыт конструктором и что вы не должны вызывать [CFile::Открытый](../../mfc/reference/cfile-class.md#open).

Вторая перегрузка действует так же, как если бы вы использовали первый конструктор и сразу же вызвали [Прикрепить](#attach) с теми же параметрами. Дополнительные сведения см. в разделе `Attach`.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCFiles#36](../../atl-mfc-shared/reference/codesnippet/cpp/cmemfile-class_1.cpp)]

## <a name="cmemfiledetach"></a><a name="detach"></a>CMemFile::Detach

Вызов ими функции, чтобы получить указатель `CMemFile`на блок памяти используется .

```
BYTE* Detach();
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на блок памяти, содержащий содержимое файла памяти.

### <a name="remarks"></a>Remarks

Вызов этой функции `CMemFile`также закрывает . Вы можете прикрепить `CMemFile` блок памяти к путем вызова [Атташе](#attach). Если вы хотите прикрепить файл и использовать данные в нем, вы должны позвонить [CFile::GetLength,](../../mfc/reference/cfile-class.md#getlength) чтобы получить длину файла, прежде чем звонить `Detach`. Обратите внимание, что если `CMemFile` вы прикрепите блок `nGrowBytes` памяти, чтобы вы могли использовать его данные (No 0), то вы не сможете вырастить файл памяти.

## <a name="cmemfilefree"></a><a name="free"></a>CMemFile::Бесплатно

Эта функция вызывается функциями-членами. `CMemFile`

```
virtual void Free(BYTE* lpMem);
```

### <a name="parameters"></a>Параметры

*lpMem*<br/>
Указатель на память, которая будет разослана.

### <a name="remarks"></a>Remarks

Переопределить эту функцию для реализации пользовательского коммонь с настройки памяти. Если вы переопределить эту функцию, вы, вероятно, хотите, чтобы переопределить [Alloc](#alloc) и [Realloc,](#realloc) а также.

## <a name="cmemfilegrowfile"></a><a name="growfile"></a>CMemFile::GrowFile

Эта функция вызывается несколькими функциями-членами. `CMemFile`

```
virtual void GrowFile(SIZE_T dwNewLen);
```

### <a name="parameters"></a>Параметры

*dwNewLen*<br/>
Новый размер файла памяти.

### <a name="remarks"></a>Remarks

Вы можете переопределить его, если `CMemFile` вы хотите изменить способ роста его файла. Реализация по умолчанию требует, чтобы [Realloc](#realloc) вырастил существующий блок (или [Alloc](#alloc) `nGrowBytes` для создания блока памяти), выделяя память в кратных значениях, указанных в вызове конструктора или [прикрепить.](#attach)

## <a name="cmemfilememcpy"></a><a name="memcpy"></a>CMemFile::Memcpy

Эта функция вызывается `CMemFile` переопределениями [CFile::Read](../../mfc/reference/cfile-class.md#read) и [CFile::Write](../../mfc/reference/cfile-class.md#write) для передачи данных в файл памяти и из нее.

```
virtual BYTE* Memcpy(
    BYTE* lpMemTarget,
    const BYTE* lpMemSource,
    SIZE_T nBytes);
```

### <a name="parameters"></a>Параметры

*lpMemTarget*<br/>
Указатель на блок памяти, в который будет скопирована память источника.

*lpMemИсточник*<br/>
Указатель на блок памяти источника.

*nБайт*<br/>
Число байтов для копирования.

### <a name="return-value"></a>Возвращаемое значение

Копия *lpMemTarget*.

### <a name="remarks"></a>Remarks

Переизобить эту функцию, `CMemFile` если вы хотите изменить способ, который делает эти копии памяти.

## <a name="cmemfilerealloc"></a><a name="realloc"></a>CMemFile::Realloc

Эта функция вызывается функциями-членами. `CMemFile`

```
virtual BYTE* Realloc(
    BYTE* lpMem,
    SIZE_T nBytes);
```

### <a name="parameters"></a>Параметры

*lpMem*<br/>
Указатель на блок памяти для перераспределения.

*nБайт*<br/>
Новый размер для блока памяти.

### <a name="return-value"></a>Возвращаемое значение

Указатель на блок памяти, который был перераспределен (и, возможно, перемещен), или NULL, если перераспределение не удалось.

### <a name="remarks"></a>Remarks

Переизбь эту функцию для реализации пользовательского перераспределения памяти. Если вы переопределить эту функцию, вы, вероятно, хотите, чтобы переопределить [Alloc](#alloc) и [бесплатно,](#free) а также.

## <a name="see-also"></a>См. также раздел

[Класс CFile](../../mfc/reference/cfile-class.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)
