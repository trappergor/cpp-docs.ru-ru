---
title: "Класс CAtlFileMappingBase | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
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
caps.latest.revision: 20
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 604a4bf49490ad2599c857eb3afd527d67e1e25b
ms.openlocfilehash: 439f123bc0addbbec2a26102d0197d0a1f14a8d5
ms.lasthandoff: 02/24/2017

---
# <a name="catlfilemappingbase-class"></a>Класс CAtlFileMappingBase
Этот класс представляет размещенный в памяти файл.  
  
> [!IMPORTANT]
>  Этот класс и его члены не может использоваться в приложениях, выполняемых в среде выполнения Windows.  
  
## <a name="syntax"></a>Синтаксис  
  
```
class CAtlFileMappingBase
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CAtlFileMappingBase::CAtlFileMappingBase](#catlfilemappingbase)|Конструктор.|  
|[CAtlFileMappingBase:: ~ CAtlFileMappingBase](#dtor)|Деструктор|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CAtlFileMappingBase::CopyFrom](#copyfrom)|Этот метод служит для копирования в объект сопоставления файлов.|  
|[CAtlFileMappingBase::GetData](#getdata)|Этот метод используется для получения данных из объекта сопоставления файлов.|  
|[CAtlFileMappingBase::GetHandle](#gethandle)|Этот метод используется для получения дескриптора файла.|  
|[CAtlFileMappingBase::GetMappingSize](#getmappingsize)|Этот метод вызывается для получения размера сопоставление в объект сопоставления файлов.|  
|[CAtlFileMappingBase::MapFile](#mapfile)|Вызовите этот метод, чтобы создать объект сопоставления файлов.|  
|[CAtlFileMappingBase::MapSharedMem](#mapsharedmem)|Этот метод вызывается для создания объекта сопоставления файлов, который предоставляет полный доступ ко всем процессам.|  
|[CAtlFileMappingBase::OpenMapping](#openmapping)|Этот метод возвращает дескриптор в объект сопоставления файлов.|  
|[CAtlFileMappingBase::Unmap](#unmap)|Этот метод используется для отмены сопоставления объект сопоставления файлов.|  
  
### <a name="public-operators"></a>Открытые операторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CAtlFileMappingBase::operator =](#operator_eq)|Задает текущий объект сопоставления файлов на другой объект сопоставления файлов.|  
  
## <a name="remarks"></a>Примечания  
 Файл сопоставления представляет собой взаимосвязь содержимого файла с частью виртуального адресного пространства процесса. Этот класс предоставляет методы для создания объектов сопоставления файлов, позволяющие приложениям легко получить доступ к и совместно использовать данные.  
  
 Дополнительные сведения см. в разделе [файла сопоставления](http://msdn.microsoft.com/library/windows/desktop/aa366556) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atlfile.h  
  
##  <a name="catlfilemappingbase"></a>CAtlFileMappingBase::CAtlFileMappingBase  
 Конструктор.  
  
```
CAtlFileMappingBase(CAtlFileMappingBase& orig);  
CAtlFileMappingBase() throw();
```  
  
### <a name="parameters"></a>Параметры  
 `orig`  
 Исходный объект сопоставления файлов для копирования для создания нового объекта.  
  
### <a name="remarks"></a>Примечания  
 Создает новый объект сопоставления файлов, при необходимости используя существующий объект. Необходимо вызвать [CAtlFileMappingBase::MapFile](#mapfile) открыть или создать объект сопоставления файлов для конкретного файла.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATL_Utilities&#71;](../../atl/codesnippet/cpp/catlfilemappingbase-class_1.cpp)]  
  
##  <a name="dtor"></a>CAtlFileMappingBase:: ~ CAtlFileMappingBase  
 Деструктор  
  
```
~CAtlFileMappingBase() throw();
```  
  
### <a name="remarks"></a>Примечания  
 Освобождает все ресурсы, выделенные класс и вызывает [CAtlFileMappingBase::Unmap](#unmap) метод.  
  
##  <a name="copyfrom"></a>CAtlFileMappingBase::CopyFrom  
 Этот метод служит для копирования в объект сопоставления файлов.  
  
```
HRESULT CopyFrom(CAtlFileMappingBase& orig) throw();
```  
  
### <a name="parameters"></a>Параметры  
 `orig`  
 Исходный объект сопоставления файлов для копирования из.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает `S_OK` на успех или ошибка `HRESULT` в случае сбоя.  
  
##  <a name="getdata"></a>CAtlFileMappingBase::GetData  
 Этот метод используется для получения данных из объекта сопоставления файлов.  
  
```
void* GetData() const throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает указатель на данные.  
  
##  <a name="gethandle"></a>CAtlFileMappingBase::GetHandle  
 Этот метод возвращает дескриптор в объект сопоставления файлов.  
  
```
HANDLE GetHandle() throw ();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает дескриптор в объект сопоставления файлов.  
  
##  <a name="getmappingsize"></a>CAtlFileMappingBase::GetMappingSize  
 Этот метод вызывается для получения размера сопоставление в объект сопоставления файлов.  
  
```
SIZE_T GetMappingSize() throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает размер сопоставления.  
  
### <a name="example"></a>Пример  
 В примере показано [CAtlFileMappingBase::CAtlFileMappingBase](#catlfilemappingbase).  
  
##  <a name="mapfile"></a>CAtlFileMappingBase::MapFile  
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
 Дескриптор файла, из которого нужно создать объект сопоставления. `hFile`должен быть допустимым и не может иметь значение INVALID_HANDLE_VALUE.  
  
 `nMappingSize`  
 Размер сопоставления. Если значение равно 0, объект сопоставления файлов максимальный размер равен текущий размер файла, определенного *hFile.*  
  
 `nOffset`  
 Смещение файла, в которой необходимо начать сопоставления. Значение смещения должен быть кратен гранулярность выделения памяти в системе.  
  
 `dwMappingProtection`  
 Защита, требуемой для просмотра файла при сопоставлении файла. В разделе `flProtect` в [CreateFileMapping](http://msdn.microsoft.com/library/windows/desktop/aa366537) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 `dwViewDesiredAccess`  
 Указывает тип доступа для просмотра файла и, следовательно, защиту страниц, сопоставляемый с помощью файла. В разделе `dwDesiredAccess` в [MapViewOfFileEx](http://msdn.microsoft.com/library/windows/desktop/aa366763) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает `S_OK` на успех или ошибка `HRESULT` в случае сбоя.  
  
### <a name="remarks"></a>Примечания  
 После создания объект сопоставления файлов размер файла не должен превышать размер объекта сопоставления файлов; в этом случае все содержимое файла не будет доступной для совместного использования. Дополнительные сведения см. в разделе [CreateFileMapping](http://msdn.microsoft.com/library/windows/desktop/aa366537) и [MapViewOfFileEx](http://msdn.microsoft.com/library/windows/desktop/aa366763) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Пример  
 В примере показано [CAtlFileMappingBase::CAtlFileMappingBase](#catlfilemappingbase).  
  
##  <a name="mapsharedmem"></a>CAtlFileMappingBase::MapSharedMem  
 Этот метод вызывается для создания объекта сопоставления файлов, который предоставляет полный доступ ко всем процессам.  
  
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
 Размер сопоставления. Если значение равно 0, максимальный размер объект сопоставления файлов равен текущий размер определяется объект сопоставления файлов`szName.`  
  
 `szName`  
 Имя объекта сопоставления.  
  
 *pbAlreadyExisted*  
 Указывает Логическое значение, равное TRUE, если объект сопоставления уже существует.  
  
 `lpsa`  
 Указатель на **SECURITY_ATTRIBUTES** структуру, определяющую, может ли возвращаемый дескриптор наследоваться дочерними процессами. В разделе *lpAttributes* в [CreateFileMapping](http://msdn.microsoft.com/library/windows/desktop/aa366537) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 `dwMappingProtection`  
 Защита, требуемой для представление файлов при сопоставлении файла. В разделе `flProtect` в **CreateFileMapping** в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 `dwViewDesiredAccess`  
 Указывает тип доступа для просмотра файла и, следовательно, защиту страниц, сопоставляемый с помощью файла. В разделе `dwDesiredAccess` в [MapViewOfFileEx](http://msdn.microsoft.com/library/windows/desktop/aa366763) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает `S_OK` на успех или ошибка `HRESULT` в случае сбоя.  
  
### <a name="remarks"></a>Примечания  
 **MapShareMem** позволяет существующий объект сопоставления файлов, созданных [CreateFileMapping](http://msdn.microsoft.com/library/windows/desktop/aa366537), чтобы совместно использоваться процессами.  
  
##  <a name="openmapping"></a>CAtlFileMappingBase::OpenMapping  
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
 Размер сопоставления. Если значение равно 0, максимальный размер объект сопоставления файлов равен текущий размер определяется объект сопоставления файлов`szName.`  
  
 `nOffset`  
 Смещение файла, в которой необходимо начать сопоставления. Значение смещения должен быть кратен гранулярность выделения памяти в системе.  
  
 `dwViewDesiredAccess`  
 Указывает тип доступа для просмотра файла и, следовательно, защиту страниц, сопоставляемый с помощью файла. В разделе `dwDesiredAccess` в [MapViewOfFileEx](http://msdn.microsoft.com/library/windows/desktop/aa366763) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает `S_OK` на успех или ошибка `HRESULT` в случае сбоя.  
  
### <a name="remarks"></a>Примечания  
 В отладочных построениях произойдет ошибка утверждения, если входные параметры являются недопустимыми.  
  
##  <a name="operator_eq"></a>CAtlFileMappingBase::operator =  
 Задает текущий объект сопоставления файлов на другой объект сопоставления файлов.  
  
```
CAtlFileMappingBase& operator=(CAtlFileMappingBase& orig);
```  
  
### <a name="parameters"></a>Параметры  
 `orig`  
 Текущий объект сопоставления файлов.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает ссылку на текущий объект.  
  
##  <a name="unmap"></a>CAtlFileMappingBase::Unmap  
 Этот метод используется для отмены сопоставления объект сопоставления файлов.  
  
```
HRESULT Unmap() throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает `S_OK` на успех или ошибка `HRESULT` в случае сбоя.  
  
### <a name="remarks"></a>Примечания  
 В разделе [UnmapViewOfFile](http://msdn.microsoft.com/library/windows/desktop/aa366882) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] для получения дополнительных сведений.  
  
## <a name="see-also"></a>См. также  
 [Класс CAtlFileMapping](../../atl/reference/catlfilemapping-class.md)   
 [Общие сведения о классе](../../atl/atl-class-overview.md)

