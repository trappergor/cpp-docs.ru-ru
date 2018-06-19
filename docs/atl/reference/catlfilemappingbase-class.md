---
title: Класс CAtlFileMappingBase | Документы Microsoft
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
ms.openlocfilehash: e315a29f72c887b5bff2e8177e7a47aed18c3fd4
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32364448"
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
  
|Имя|Описание|  
|----------|-----------------|  
|[CAtlFileMappingBase::CAtlFileMappingBase](#catlfilemappingbase)|Конструктор.|  
|[CAtlFileMappingBase:: ~ CAtlFileMappingBase](#dtor)|Деструктор|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CAtlFileMappingBase::CopyFrom](#copyfrom)|Этот метод используется для копирования из объект сопоставления файлов.|  
|[CAtlFileMappingBase::GetData](#getdata)|Этот метод вызывается для получения данных из объекта сопоставления файлов.|  
|[CAtlFileMappingBase::GetHandle](#gethandle)|Этот метод используется для получения дескриптора файла.|  
|[CAtlFileMappingBase::GetMappingSize](#getmappingsize)|Этот метод вызывается для получения размера сопоставления из объекта сопоставления файлов.|  
|[CAtlFileMappingBase::MapFile](#mapfile)|Вызовите этот метод, чтобы создать объект сопоставления файлов.|  
|[CAtlFileMappingBase::MapSharedMem](#mapsharedmem)|Вызовите этот метод, чтобы создать объект сопоставления файлов, который предоставляет полный доступ ко всем процессам.|  
|[CAtlFileMappingBase::OpenMapping](#openmapping)|Этот метод возвращает дескриптор в объект сопоставления файлов.|  
|[CAtlFileMappingBase::Unmap](#unmap)|Этот метод вызывается для отмены сопоставления объект сопоставления файлов.|  
  
### <a name="public-operators"></a>Открытые операторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CAtlFileMappingBase::operator =](#operator_eq)|Задает текущий объект сопоставления файлов на другой объект сопоставления файлов.|  
  
## <a name="remarks"></a>Примечания  
 Файл сопоставления представляет собой взаимосвязь содержимого файла с областью виртуального адресного пространства процесса. Этот класс предоставляет методы для создания объектов сопоставления файлов, которые разрешить программам легко доступ и совместное использование данных.  
  
 Дополнительные сведения см. в разделе [сопоставлению файла](http://msdn.microsoft.com/library/windows/desktop/aa366556) в Windows SDK.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atlfile.h  
  
##  <a name="catlfilemappingbase"></a>  CAtlFileMappingBase::CAtlFileMappingBase  
 Конструктор.  
  
```
CAtlFileMappingBase(CAtlFileMappingBase& orig);  
CAtlFileMappingBase() throw();
```  
  
### <a name="parameters"></a>Параметры  
 `orig`  
 Исходный объект сопоставления файлов для копирования для создания нового объекта.  
  
### <a name="remarks"></a>Примечания  
 Создает новый объект сопоставления файлов, при необходимости с помощью существующего объекта. Необходимо вызвать [CAtlFileMappingBase::MapFile](#mapfile) открыть или создать объект сопоставления файлов для конкретного файла.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATL_Utilities#71](../../atl/codesnippet/cpp/catlfilemappingbase-class_1.cpp)]  
  
##  <a name="dtor"></a>  CAtlFileMappingBase:: ~ CAtlFileMappingBase  
 Деструктор  
  
```
~CAtlFileMappingBase() throw();
```  
  
### <a name="remarks"></a>Примечания  
 Освобождает все ресурсы, выделенные класса и вызывает [CAtlFileMappingBase::Unmap](#unmap) метод.  
  
##  <a name="copyfrom"></a>  CAtlFileMappingBase::CopyFrom  
 Этот метод используется для копирования из объект сопоставления файлов.  
  
```
HRESULT CopyFrom(CAtlFileMappingBase& orig) throw();
```  
  
### <a name="parameters"></a>Параметры  
 `orig`  
 Исходный объект сопоставления файлов для копирования из.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает `S_OK` на успех или ошибка `HRESULT` при сбое.  
  
##  <a name="getdata"></a>  CAtlFileMappingBase::GetData  
 Этот метод вызывается для получения данных из объекта сопоставления файлов.  
  
```
void* GetData() const throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает указатель на данные.  
  
##  <a name="gethandle"></a>  CAtlFileMappingBase::GetHandle  
 Этот метод возвращает дескриптор в объект сопоставления файлов.  
  
```
HANDLE GetHandle() throw ();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает дескриптор в объект сопоставления файлов.  
  
##  <a name="getmappingsize"></a>  CAtlFileMappingBase::GetMappingSize  
 Этот метод вызывается для получения размера сопоставления из объекта сопоставления файлов.  
  
```
SIZE_T GetMappingSize() throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает размер сопоставления.  
  
### <a name="example"></a>Пример  
 Далее приведен пример [CAtlFileMappingBase::CAtlFileMappingBase](#catlfilemappingbase).  
  
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
 `hFile`  
 Дескриптор файла, из которого необходимо создать объект сопоставления. `hFile` должен быть допустимым и не может быть значение INVALID_HANDLE_VALUE.  
  
 `nMappingSize`  
 Размер сопоставления. Если значение равно 0, объект сопоставления файлов максимальный размер равен текущий размер файла, определенного *hFile.*  
  
 `nOffset`  
 Смещение файла, в котором начинается сопоставления. Значение смещения должно быть кратно гранулярность выделения памяти в системе.  
  
 `dwMappingProtection`  
 Защита, требуемого для просмотра файла, при сопоставлении файла. В разделе `flProtect` в [CreateFileMapping](http://msdn.microsoft.com/library/windows/desktop/aa366537) в Windows SDK.  
  
 `dwViewDesiredAccess`  
 Указывает тип доступа для просмотра файла и, следовательно, защиту страниц, сопоставляемый с помощью файла. В разделе `dwDesiredAccess` в [MapViewOfFileEx](http://msdn.microsoft.com/library/windows/desktop/aa366763) в Windows SDK.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает `S_OK` на успех или ошибка `HRESULT` при сбое.  
  
### <a name="remarks"></a>Примечания  
 После создания объект сопоставления файлов, размер файла не должен превышать размер объекта сопоставления файлов; в этом случае все содержимое файла не предоставляется для общего доступа. Дополнительные сведения см. в разделе [CreateFileMapping](http://msdn.microsoft.com/library/windows/desktop/aa366537) и [MapViewOfFileEx](http://msdn.microsoft.com/library/windows/desktop/aa366763) в Windows SDK.  
  
### <a name="example"></a>Пример  
 Далее приведен пример [CAtlFileMappingBase::CAtlFileMappingBase](#catlfilemappingbase).  
  
##  <a name="mapsharedmem"></a>  CAtlFileMappingBase::MapSharedMem  
 Вызовите этот метод, чтобы создать объект сопоставления файлов, который предоставляет полный доступ ко всем процессам.  
  
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
 `nMappingSize`  
 Размер сопоставления. Если значение равно 0, максимальный размер объекта сопоставления файлов равен текущий размер определяется объект сопоставления файлов `szName.`  
  
 `szName`  
 Имя объекта сопоставления.  
  
 *pbAlreadyExisted*  
 Указывает Логическое значение, имеет значение TRUE, если объект сопоставление уже существует.  
  
 `lpsa`  
 Указатель на **SECURITY_ATTRIBUTES** структуру, которая определяет, может ли возвращаемый дескриптор наследоваться дочерними процессами. В разделе *lpAttributes* в [CreateFileMapping](http://msdn.microsoft.com/library/windows/desktop/aa366537) в Windows SDK.  
  
 `dwMappingProtection`  
 Защита, требуемого для представления файла, при сопоставлении файла. В разделе `flProtect` в **CreateFileMapping** в Windows SDK.  
  
 `dwViewDesiredAccess`  
 Указывает тип доступа для просмотра файла и, следовательно, защиту страниц, сопоставляемый с помощью файла. В разделе `dwDesiredAccess` в [MapViewOfFileEx](http://msdn.microsoft.com/library/windows/desktop/aa366763) в Windows SDK.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает `S_OK` на успех или ошибка `HRESULT` при сбое.  
  
### <a name="remarks"></a>Примечания  
 **MapShareMem** позволяет существующий объект сопоставления файлов, созданных [CreateFileMapping](http://msdn.microsoft.com/library/windows/desktop/aa366537), чтобы одновременно несколькими процессами.  
  
##  <a name="openmapping"></a>  CAtlFileMappingBase::OpenMapping  
 Вызовите этот метод, чтобы открыть именованный объект сопоставления файлов для указанного файла.  
  
```
HRESULT OpenMapping(
    LPCTSTR szName,
    SIZE_T nMappingSize,
    ULONGLONG nOffset = 0,
    DWORD dwViewDesiredAccess = FILE_MAP_ALL_ACCESS) throw();
```  
  
### <a name="parameters"></a>Параметры  
 `szName`  
 Имя объекта сопоставления. Если имеется открытый дескриптор в объект сопоставления файлов с таким именем и дескриптор безопасности для объекта сопоставления не конфликтует с `dwViewDesiredAccess` параметр, откройте операция выполнена успешно.  
  
 `nMappingSize`  
 Размер сопоставления. Если значение равно 0, максимальный размер объекта сопоставления файлов равен текущий размер определяется объект сопоставления файлов `szName.`  
  
 `nOffset`  
 Смещение файла, в котором начинается сопоставления. Значение смещения должно быть кратно гранулярность выделения памяти в системе.  
  
 `dwViewDesiredAccess`  
 Указывает тип доступа для просмотра файла и, следовательно, защиту страниц, сопоставляемый с помощью файла. В разделе `dwDesiredAccess` в [MapViewOfFileEx](http://msdn.microsoft.com/library/windows/desktop/aa366763) в Windows SDK.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает `S_OK` на успех или ошибка `HRESULT` при сбое.  
  
### <a name="remarks"></a>Примечания  
 В отладочных построениях произойдет ошибка утверждения, если входные параметры являются недопустимыми.  
  
##  <a name="operator_eq"></a>  CAtlFileMappingBase::operator =  
 Задает текущий объект сопоставления файлов на другой объект сопоставления файлов.  
  
```
CAtlFileMappingBase& operator=(CAtlFileMappingBase& orig);
```  
  
### <a name="parameters"></a>Параметры  
 `orig`  
 Текущий объект сопоставления файлов.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает ссылку на текущий объект.  
  
##  <a name="unmap"></a>  CAtlFileMappingBase::Unmap  
 Этот метод вызывается для отмены сопоставления объект сопоставления файлов.  
  
```
HRESULT Unmap() throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает `S_OK` на успех или ошибка `HRESULT` при сбое.  
  
### <a name="remarks"></a>Примечания  
 В разделе [UnmapViewOfFile](http://msdn.microsoft.com/library/windows/desktop/aa366882) в Windows SDK для получения дополнительных сведений.  
  
## <a name="see-also"></a>См. также  
 [Класс CAtlFileMapping](../../atl/reference/catlfilemapping-class.md)   
 [Общие сведения о классе](../../atl/atl-class-overview.md)
