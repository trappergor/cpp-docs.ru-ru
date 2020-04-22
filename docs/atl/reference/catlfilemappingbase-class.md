---
title: Класс CAtlFileMappingBase
ms.date: 11/04/2016
f1_keywords:
- CAtlFileMappingBase
- ATLFILE/ATL::CAtlFileMappingBase
- ATLFILE/ATL::CAtlFileMappingBase::CAtlFileMappingBase
- ATLFILE/ATL::CAtlFileMappingBase::CopyFrom
- ATLFILE/ATL::CAtlFileMappingBase::GetData
- ATLFILE/ATL::CAtlFileMappingBase::GetHandle
- ATLFILE/ATL::CAtlFileMappingBase::GetMappingSize
- ATLFILE/ATL::CAtlFileMappingBase::MapFile
- ATLFILE/ATL::CAtlFileMappingBase::MapSharedMem
- ATLFILE/ATL::CAtlFileMappingBase::OpenMapping
- ATLFILE/ATL::CAtlFileMappingBase::Unmap
helpviewer_keywords:
- CAtlFileMappingBase class
ms.assetid: be555723-2790-4f57-a8fb-be4d68460775
ms.openlocfilehash: 16eebfff4330a47888d1b60eaa993ee87d120f72
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2020
ms.locfileid: "81748297"
---
# <a name="catlfilemappingbase-class"></a>Класс CAtlFileMappingBase

Этот класс представляет собой файл с картографированным памятью.

> [!IMPORTANT]
> Этот класс и его члены не могут быть использованы в приложениях, выполняемых в Windows Runtime.

## <a name="syntax"></a>Синтаксис

```
class CAtlFileMappingBase
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CAtlFileMappingBase::CAtlFileMappingBase](#catlfilemappingbase)|Конструктор.|
|[CAtlFileMappingBase::: »CAtlFileMappingBase](#dtor)|Деструктор|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CAtlFileMappingBase:CopyFrom](#copyfrom)|Вызовите этот метод для копирования с объекта отображения файлов.|
|[CAtlFileMappingBase::GetData](#getdata)|Вызовите этот метод, чтобы получить данные с объекта картирования файлов.|
|[CAtlFileMappingBase::GetHandle](#gethandle)|Вызовите этот метод, чтобы вернуть ручку файла.|
|[CAtlFileMappingBase::GetMappingSize](#getmappingsize)|Вызовите этот метод, чтобы получить размер отображения от объекта отображения файлов.|
|[CAtlFileMappingBase:MapFile](#mapfile)|Вызовите этот метод для создания объекта отображения файлов.|
|[CAtlFileMappingBase::MapSharedMem](#mapsharedmem)|Вызовите этот метод, чтобы создать объект отображения файлов, который обеспечивает полный доступ ко всем процессам.|
|[CAtlFileMappingBase::OpenMapping](#openmapping)|Вызовите этот метод, чтобы вернуть ручку объекту отображения файлов.|
|[CAtlFileMappingBase::Unmap](#unmap)|Вызовите этот метод, чтобы отображение карты объекта отображения файлов.|

### <a name="public-operators"></a>Открытые операторы

|Имя|Описание|
|----------|-----------------|
|[CAtlFileMappingBase::оператор](#operator_eq)|Устанавливает текущий объект отображения файлов на другой объект отображения файлов.|

## <a name="remarks"></a>Remarks

Отображение файлов — это связь содержимого файла с частью виртуального адресного пространства процесса. Этот класс предоставляет методы создания объектов картирования файлов, которые позволяют программам легко получать доступ к данным и обмениваться ими.

Для получения дополнительной информации смотрите [файловое картирование](/windows/win32/Memory/file-mapping) в SDK Windows.

## <a name="requirements"></a>Требования

**Заголовок:** atlfile.h

## <a name="catlfilemappingbasecatlfilemappingbase"></a><a name="catlfilemappingbase"></a>CAtlFileMappingBase::CAtlFileMappingBase

Конструктор.

```
CAtlFileMappingBase(CAtlFileMappingBase& orig);
CAtlFileMappingBase() throw();
```

### <a name="parameters"></a>Параметры

*Orig*<br/>
Исходный объект отображения файлов для копирования для создания нового объекта.

### <a name="remarks"></a>Remarks

Создает новый объект отображения файлов, по желанию используя существующий объект. По-прежнему необходимо вызвать [CAtlFileMappingBase::MapFile,](#mapfile) чтобы открыть или создать объект отображения файлов для конкретного файла.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_Utilities#71](../../atl/codesnippet/cpp/catlfilemappingbase-class_1.cpp)]

## <a name="catlfilemappingbasecatlfilemappingbase"></a><a name="dtor"></a>CAtlFileMappingBase::: »CAtlFileMappingBase

Деструктор

```
~CAtlFileMappingBase() throw();
```

### <a name="remarks"></a>Remarks

Освобождает все ресурсы, выделенные классом, и вызывает [метод CAtlFileMappingBase::Unmap.](#unmap)

## <a name="catlfilemappingbasecopyfrom"></a><a name="copyfrom"></a>CAtlFileMappingBase:CopyFrom

Вызовите этот метод для копирования с объекта отображения файлов.

```
HRESULT CopyFrom(CAtlFileMappingBase& orig) throw();
```

### <a name="parameters"></a>Параметры

*Orig*<br/>
Исходный объект отображения файлов для копирования.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK на успех, или ошибка HRESULT на отказ.

## <a name="catlfilemappingbasegetdata"></a><a name="getdata"></a>CAtlFileMappingBase::GetData

Вызовите этот метод, чтобы получить данные с объекта картирования файлов.

```cpp
void* GetData() const throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает указатель к данным.

## <a name="catlfilemappingbasegethandle"></a><a name="gethandle"></a>CAtlFileMappingBase::GetHandle

Вызовите этот метод, чтобы вернуть ручку объекту отображения файлов.

```
HANDLE GetHandle() throw ();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает ручку объекту отображения файлов.

## <a name="catlfilemappingbasegetmappingsize"></a><a name="getmappingsize"></a>CAtlFileMappingBase::GetMappingSize

Вызовите этот метод, чтобы получить размер отображения от объекта отображения файлов.

```
SIZE_T GetMappingSize() throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает размер отображения.

### <a name="example"></a>Пример

Смотрите пример [для CAtlFileMappingBase::CAtlFileMappingBase](#catlfilemappingbase).

## <a name="catlfilemappingbasemapfile"></a><a name="mapfile"></a>CAtlFileMappingBase:MapFile

Вызовите этот метод, чтобы открыть или создать объект отображения файлов для указанного файла.

```
HRESULT MapFile(
    HANDLE hFile,
    SIZE_T nMappingSize = 0,
    ULONGLONG nOffset = 0,
    DWORD dwMappingProtection = PAGE_READONLY,
    DWORD dwViewDesiredAccess = FILE_MAP_READ) throw();
```

### <a name="parameters"></a>Параметры

*hFile*<br/>
Обработка файла, из которого можно создать объект отображения. *hFile* должен быть действительным и не может быть установлен на INVALID_HANDLE_VALUE.

*nMappingРазмер*<br/>
Размер отображения. Если 0, максимальный размер объекта отображения файлов равен текущему размеру файла, идентифицированному *hFile.*

*nOffset*<br/>
Файл смещения, где отображение, чтобы начать. Смещенное значение должно быть кратным детализации распределения памяти системы.

*dwMappingЗащита*<br/>
Защита, желаемая для представления файла при составлении карты файла. Смотрите *flProtect* в [CreateFileMapping](/windows/win32/api/winbase/nf-winbase-createfilemappinga) в Windows SDK.

*dwViewDesiredAccess*<br/>
Определяет тип доступа к представлению файла и, следовательно, защиту страниц, отображаемых файлом. Смотрите *dwDesiredAccess* в [MapViewOfFileEx](/windows/win32/api/memoryapi/nf-memoryapi-mapviewoffileex) в Windows SDK.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK на успех, или ошибка HRESULT на отказ.

### <a name="remarks"></a>Remarks

После создания объекта отображения файлов размер файла не должен превышать размер объекта отображения файлов; если это так, не все содержимое файла будет доступно для совместного использования. Для получения более подробной информации смотрите [CreateFileMapping](/windows/win32/api/winbase/nf-winbase-createfilemappinga) и [MapViewOfFileEx](/windows/win32/api/memoryapi/nf-memoryapi-mapviewoffileex) в SDK Windows.

### <a name="example"></a>Пример

Смотрите пример [для CAtlFileMappingBase::CAtlFileMappingBase](#catlfilemappingbase).

## <a name="catlfilemappingbasemapsharedmem"></a><a name="mapsharedmem"></a>CAtlFileMappingBase::MapSharedMem

Вызовите этот метод, чтобы создать объект отображения файлов, который обеспечивает полный доступ ко всем процессам.

```
HRESULT MapSharedMem(
    SIZE_T nMappingSize,
    LPCTSTR szName,
    BOOL* pbAlreadyExisted = NULL,
    LPSECURITY_ATTRIBUTES lpsa = NULL,
    DWORD dwMappingProtection = PAGE_READWRITE,
    DWORD dwViewDesiredAccess = FILE_MAP_ALL_ACCESS) throw();
```

### <a name="parameters"></a>Параметры

*nMappingРазмер*<br/>
Размер отображения. При 0 максимальном размере объекта отображения файлов равен текущему размеру объекта отображения файлов, идентифицированному *szName.*

*szName*<br/>
Название объекта отображения.

*pbAlreadyExisted*<br/>
Указывает на значение BOOL, которое устанавливается в TRUE, если объект отображения уже существует.

*лза*<br/>
Указатель на `SECURITY_ATTRIBUTES` структуру, определяющую, может ли возвращенная ручка быть унаследована детскими процессами. Смотрите *lpAttributes* в [CreateFileMapping](/windows/win32/api/winbase/nf-winbase-createfilemappinga) в Windows SDK.

*dwMappingЗащита*<br/>
Защита, желаемая для представления файла, при составлении файла на карте. Смотрите *flProtect* в `CreateFileMapping` Windows SDK.

*dwViewDesiredAccess*<br/>
Определяет тип доступа к представлению файла и, следовательно, защиту страниц, отображаемых файлом. Смотрите *dwDesiredAccess* в [MapViewOfFileEx](/windows/win32/api/memoryapi/nf-memoryapi-mapviewoffileex) в Windows SDK.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK на успех, или ошибка HRESULT на отказ.

### <a name="remarks"></a>Remarks

`MapShareMem`позволяет передавать существующий объект отображения файлов, созданный [CreateFileMapping,](/windows/win32/api/winbase/nf-winbase-createfilemappinga)между процессами.

## <a name="catlfilemappingbaseopenmapping"></a><a name="openmapping"></a>CAtlFileMappingBase::OpenMapping

Вызовите этот метод, чтобы открыть названный объект отображения файлов для указанного файла.

```
HRESULT OpenMapping(
    LPCTSTR szName,
    SIZE_T nMappingSize,
    ULONGLONG nOffset = 0,
    DWORD dwViewDesiredAccess = FILE_MAP_ALL_ACCESS) throw();
```

### <a name="parameters"></a>Параметры

*szName*<br/>
Название объекта отображения. Если есть открытая ручка к объекту отображения файлов с этим именем и дескриптор безопасности на объекте отображения не противоречит параметру *dwViewDesiredAccess,* открытая операция удавляется.

*nMappingРазмер*<br/>
Размер отображения. При 0 максимальном размере объекта отображения файлов равен текущему размеру объекта отображения файлов, идентифицированному *szName.*

*nOffset*<br/>
Файл смещения, где отображение, чтобы начать. Смещенное значение должно быть кратным детализации распределения памяти системы.

*dwViewDesiredAccess*<br/>
Определяет тип доступа к представлению файла и, следовательно, защиту страниц, отображаемых файлом. Смотрите *dwDesiredAccess* в [MapViewOfFileEx](/windows/win32/api/memoryapi/nf-memoryapi-mapviewoffileex) в Windows SDK.

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK на успех, или ошибка HRESULT на отказ.

### <a name="remarks"></a>Remarks

В отладке сборки возникает ошибка утверждения, если параметры ввода недействительны.

## <a name="catlfilemappingbaseoperator-"></a><a name="operator_eq"></a>CAtlFileMappingBase::оператор

Устанавливает текущий объект отображения файлов на другой объект отображения файлов.

```
CAtlFileMappingBase& operator=(CAtlFileMappingBase& orig);
```

### <a name="parameters"></a>Параметры

*Orig*<br/>
Текущий объект отображения файлов.

### <a name="return-value"></a>Возвращаемое значение

Возвращает ссылку на текущий объект.

## <a name="catlfilemappingbaseunmap"></a><a name="unmap"></a>CAtlFileMappingBase::Unmap

Вызовите этот метод, чтобы отображение карты объекта отображения файлов.

```
HRESULT Unmap() throw();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает S_OK на успех, или ошибка HRESULT на отказ.

### <a name="remarks"></a>Remarks

Более [подробную](/windows/win32/api/memoryapi/nf-memoryapi-unmapviewoffile) информацию можно узнать в SDK для Windows.

## <a name="see-also"></a>См. также раздел

[Класс CAtlFileMapping](../../atl/reference/catlfilemapping-class.md)<br/>
[Общие сведения о классах](../../atl/atl-class-overview.md)
