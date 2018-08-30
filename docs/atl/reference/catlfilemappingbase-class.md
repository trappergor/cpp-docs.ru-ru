---
title: Класс CAtlFileMappingBase | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- CAtlFileMappingBase class
ms.assetid: be555723-2790-4f57-a8fb-be4d68460775
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 8f07f14cca7ea0346cc6772d3dca959af07a05cd
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/29/2018
ms.locfileid: "43218166"
---
# <a name="catlfilemappingbase-class"></a>Класс CAtlFileMappingBase
Этот класс представляет файл, размещенный в памяти.  
  
> [!IMPORTANT]
>  Этот класс и его члены не может использоваться в приложениях, выполняемых в среде выполнения Windows.  
  
## <a name="syntax"></a>Синтаксис  
  
```
class CAtlFileMappingBase
```  
  
## <a name="members"></a>Участники  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CAtlFileMappingBase::CAtlFileMappingBase](#catlfilemappingbase)|Конструктор.|  
|[CAtlFileMappingBase:: ~ CAtlFileMappingBase](#dtor)|Деструктор|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CAtlFileMappingBase::CopyFrom](#copyfrom)|Этот метод используется для копирования из объекта сопоставления файлов.|  
|[CAtlFileMappingBase::GetData](#getdata)|Этот метод используется для получения данных из объекта сопоставления файлов.|  
|[CAtlFileMappingBase::GetHandle](#gethandle)|Этот метод используется для возврата дескриптора файла.|  
|[CAtlFileMappingBase::GetMappingSize](#getmappingsize)|Вызовите этот метод, чтобы задать размер сопоставления из объекта сопоставления файлов.|  
|[CAtlFileMappingBase::MapFile](#mapfile)|Вызовите этот метод, чтобы создать объект сопоставления файлов.|  
|[CAtlFileMappingBase::MapSharedMem](#mapsharedmem)|Вызовите этот метод, чтобы создать объект сопоставления файлов, который обеспечивает полный доступ ко всем процессам.|  
|[CAtlFileMappingBase::OpenMapping](#openmapping)|Этот метод возвращает дескриптор для объекта сопоставления файлов.|  
|[CAtlFileMappingBase::Unmap](#unmap)|Вызовите этот метод, чтобы отменить сопоставление объект сопоставления файлов.|  
  
### <a name="public-operators"></a>Открытые операторы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CAtlFileMappingBase::operator =](#operator_eq)|Задает текущий объект сопоставления файлов на другой объект сопоставления файлов.|  
  
## <a name="remarks"></a>Примечания  
 Файл сопоставления представляет собой взаимосвязь содержимого файла с частью виртуального адресного пространства процесса. Этот класс предоставляет методы для создания объектов сопоставления файлов, которые разрешают приложениям легко получить доступ к и совместно использовать данные.  
  
 Дополнительные сведения см. в разделе [сопоставление файла](/windows/desktop/Memory/file-mapping) в пакете Windows SDK.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atlfile.h  
  
##  <a name="catlfilemappingbase"></a>  CAtlFileMappingBase::CAtlFileMappingBase  
 Конструктор.  
  
```
CAtlFileMappingBase(CAtlFileMappingBase& orig);  
CAtlFileMappingBase() throw();
```  
  
### <a name="parameters"></a>Параметры  
 *ORIG*  
 Исходный объект сопоставления файлов для копирования для создания нового объекта.  
  
### <a name="remarks"></a>Примечания  
 Создает новый объект сопоставления файлов, при необходимости используя существующий объект. По-прежнему необходимо вызвать [CAtlFileMappingBase::MapFile](#mapfile) открыть или создать объект сопоставления файлов для конкретного файла.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATL_Utilities#71](../../atl/codesnippet/cpp/catlfilemappingbase-class_1.cpp)]  
  
##  <a name="dtor"></a>  CAtlFileMappingBase:: ~ CAtlFileMappingBase  
 Деструктор  
  
```
~CAtlFileMappingBase() throw();
```  
  
### <a name="remarks"></a>Примечания  
 Освобождает все ресурсы, распределенные по классу и вызовы [CAtlFileMappingBase::Unmap](#unmap) метод.  
  
##  <a name="copyfrom"></a>  CAtlFileMappingBase::CopyFrom  
 Этот метод используется для копирования из объекта сопоставления файлов.  
  
```
HRESULT CopyFrom(CAtlFileMappingBase& orig) throw();
```  
  
### <a name="parameters"></a>Параметры  
 *ORIG*  
 Исходный объект сопоставления файлов для копирования из.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает S_OK в случае успеха или ошибки HRESULT в случае сбоя.  
  
##  <a name="getdata"></a>  CAtlFileMappingBase::GetData  
 Этот метод используется для получения данных из объекта сопоставления файлов.  
  
```
void* GetData() const throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает указатель на данные.  
  
##  <a name="gethandle"></a>  CAtlFileMappingBase::GetHandle  
 Этот метод возвращает дескриптор для объекта сопоставления файлов.  
  
```
HANDLE GetHandle() throw ();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает дескриптор для объекта сопоставления файлов.  
  
##  <a name="getmappingsize"></a>  CAtlFileMappingBase::GetMappingSize  
 Вызовите этот метод, чтобы задать размер сопоставления из объекта сопоставления файлов.  
  
```
SIZE_T GetMappingSize() throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает размер сопоставления.  
  
### <a name="example"></a>Пример  
 См. в примере [CAtlFileMappingBase::CAtlFileMappingBase](#catlfilemappingbase).  
  
##  <a name="mapfile"></a>  CAtlFileMappingBase::MapFile  
 Вызовите этот метод, чтобы открыть или создать объект сопоставления файлов для указанного файла.  
  
```
HRESULT MapFile(
    HANDLE hFile,
    SIZE_T nMappingSize = 0,
    ULONGLONG nOffset = 0,
    DWORD dwMappingProtection = PAGE_READONLY,
    DWORD dwViewDesiredAccess = FILE_MAP_READ) throw();
```  
  
### <a name="parameters"></a>Параметры  
 *hFile*  
 Дескриптор файла, из которого создается объект сопоставления. *hFile* должен быть допустимым и не может быть присвоено значение INVALID_HANDLE_VALUE.  
  
 *nMappingSize*  
 Размер сопоставления. Если значение равно 0, объект сопоставления файлов максимальный размер равен текущий размер файла, определенного *hFile.*  
  
 *nOffset*  
 Смещение файла, в котором начинается сопоставление. Значение смещения должно быть кратно гранулярность выделения памяти системы.  
  
 *dwMappingProtection*  
 Защита, требуемого для представления файла, при сопоставлении файла. См. в разделе *flProtect* в [CreateFileMapping](/windows/desktop/api/winbase/nf-winbase-createfilemappinga) в пакете Windows SDK.  
  
 *dwViewDesiredAccess*  
 Указывает тип доступа для представления файла и, следовательно, защиту страниц, сопоставляемый с помощью файла. См. в разделе *dwDesiredAccess* в [MapViewOfFileEx](https://msdn.microsoft.com/library/windows/desktop/aa366763) в пакете Windows SDK.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает S_OK в случае успеха или ошибки HRESULT в случае сбоя.  
  
### <a name="remarks"></a>Примечания  
 После создания объект сопоставления файлов, размер файла не должен превышать размер объекта сопоставления файлов; в этом случае не все содержимое файла будут доступны для совместного использования. Дополнительные сведения см. в разделе [CreateFileMapping](/windows/desktop/api/winbase/nf-winbase-createfilemappinga) и [MapViewOfFileEx](https://msdn.microsoft.com/library/windows/desktop/aa366763) в пакете Windows SDK.  
  
### <a name="example"></a>Пример  
 См. в примере [CAtlFileMappingBase::CAtlFileMappingBase](#catlfilemappingbase).  
  
##  <a name="mapsharedmem"></a>  CAtlFileMappingBase::MapSharedMem  
 Вызовите этот метод, чтобы создать объект сопоставления файлов, который обеспечивает полный доступ ко всем процессам.  
  
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
 *nMappingSize*  
 Размер сопоставления. Если значение равно 0, максимальный размер объекта сопоставления файлов равен текущий размер сопоставления файлов объекта, идентифицируемое по *szName*.  
  
 *szName*  
 Имя объекта сопоставления.  
  
 *pbAlreadyExisted*  
 Указывает на значение BOOL, которой присваивается значение TRUE, если объект сопоставления уже существует.  
  
 *lpsa*  
 Указатель на `SECURITY_ATTRIBUTES` структуру, которая указывает, может ли возвращаемый дескриптор быть унаследован дочерними процессами. См. в разделе *lpAttributes* в [CreateFileMapping](/windows/desktop/api/winbase/nf-winbase-createfilemappinga) в пакете Windows SDK.  
  
 *dwMappingProtection*  
 Защита, требуемого для представления файла, при сопоставлении файла. См. в разделе *flProtect* в `CreateFileMapping` в пакете Windows SDK.  
  
 *dwViewDesiredAccess*  
 Указывает тип доступа для представления файла и, следовательно, защиту страниц, сопоставляемый с помощью файла. См. в разделе *dwDesiredAccess* в [MapViewOfFileEx](https://msdn.microsoft.com/library/windows/desktop/aa366763) в пакете Windows SDK.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает S_OK в случае успеха или ошибки HRESULT в случае сбоя.  
  
### <a name="remarks"></a>Примечания  
 `MapShareMem` позволяет существующий объект сопоставления файлов, созданных [CreateFileMapping](/windows/desktop/api/winbase/nf-winbase-createfilemappinga), чтобы быть совместно использоваться несколькими процессами.  
  
##  <a name="openmapping"></a>  CAtlFileMappingBase::OpenMapping  
 Вызовите этот метод, чтобы открыть объект сопоставления файлов с именем для указанного файла.  
  
```
HRESULT OpenMapping(
    LPCTSTR szName,
    SIZE_T nMappingSize,
    ULONGLONG nOffset = 0,
    DWORD dwViewDesiredAccess = FILE_MAP_ALL_ACCESS) throw();
```  
  
### <a name="parameters"></a>Параметры  
 *szName*  
 Имя объекта сопоставления. Если имеется открытый дескриптор в объект сопоставления файлов с таким именем и дескриптор безопасности в объект сопоставления не конфликтует с *dwViewDesiredAccess* параметр, откройте операция прошла успешно.  
  
 *nMappingSize*  
 Размер сопоставления. Если значение равно 0, максимальный размер объекта сопоставления файлов равен текущий размер сопоставления файлов объекта, идентифицируемое по *szName*.  
  
 *nOffset*  
 Смещение файла, в котором начинается сопоставление. Значение смещения должно быть кратно гранулярность выделения памяти системы.  
  
 *dwViewDesiredAccess*  
 Указывает тип доступа для представления файла и, следовательно, защиту страниц, сопоставляемый с помощью файла. См. в разделе *dwDesiredAccess* в [MapViewOfFileEx](https://msdn.microsoft.com/library/windows/desktop/aa366763) в пакете Windows SDK.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает S_OK в случае успеха или ошибки HRESULT в случае сбоя.  
  
### <a name="remarks"></a>Примечания  
 В отладочных сборках произойдет ошибка утверждения, если входные параметры являются недопустимыми.  
  
##  <a name="operator_eq"></a>  CAtlFileMappingBase::operator =  
 Задает текущий объект сопоставления файлов на другой объект сопоставления файлов.  
  
```
CAtlFileMappingBase& operator=(CAtlFileMappingBase& orig);
```  
  
### <a name="parameters"></a>Параметры  
 *ORIG*  
 Текущий объект сопоставления файлов.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает ссылку на текущий объект.  
  
##  <a name="unmap"></a>  CAtlFileMappingBase::Unmap  
 Вызовите этот метод, чтобы отменить сопоставление объект сопоставления файлов.  
  
```
HRESULT Unmap() throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает S_OK в случае успеха или ошибки HRESULT в случае сбоя.  
  
### <a name="remarks"></a>Примечания  
 См. в разделе [UnmapViewOfFile](https://msdn.microsoft.com/library/windows/desktop/aa366882) в пакете SDK Windows для получения дополнительных сведений.  
  
## <a name="see-also"></a>См. также  
 [Класс CAtlFileMapping](../../atl/reference/catlfilemapping-class.md)   
 [Общие сведения о классе](../../atl/atl-class-overview.md)
