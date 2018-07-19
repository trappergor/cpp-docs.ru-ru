---
title: Метод FtmBase::GetMarshalSizeMax | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- ftm/Microsoft::WRL::FtmBase::GetMarshalSizeMax
dev_langs:
- C++
helpviewer_keywords:
- GetMarshalSizeMax method
ms.assetid: b416b1bf-c73e-45d5-abb8-04921c1a0c94
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 5a298e63bc67dadf33a5e653d0eecf165a530d82
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2018
ms.locfileid: "33873798"
---
# <a name="ftmbasegetmarshalsizemax-method"></a>Метод FtmBase::GetMarshalSizeMax
Верхняя граница получите число байтов, необходимое для маршалинга заданный указатель интерфейса на указанный объект.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
STDMETHODIMP GetMarshalSizeMax(  
   __in REFIID riid,  
   __in_opt void *pv,  
   __in DWORD dwDestContext,  
   __reserved void *pvDestContext,  
   __in DWORD mshlflags,  
   __out DWORD *pSize  
) override;  
```  
  
#### <a name="parameters"></a>Параметры  
 `riid`  
 Ссылка на идентификатор интерфейса, который необходимо маршалировать.  
  
 `pv`  
 Указатель на интерфейс для маршалинга; может иметь значение NULL.  
  
 `dwDestContext`  
 Контекст назначения, где должна быть распаковать указанный интерфейс.  
  
 Укажите одно или несколько значений перечисления MSHCTX.  
  
 В настоящее время распаковка может произойти в другое подразделение (MSHCTX_INPROC) текущего процесса или в другом процессе на том же компьютере, как текущий процесс (MSHCTX_LOCAL).  
  
 `pvDestContext`  
 Зарезервировано для будущего использования; должен иметь значение NULL.  
  
 `mshlflags`  
 Флаг, указывающий, будет ли передаваться обратно в процессе клиента данные для маршалинга — типичный случай — диска или записываются на глобальной таблицы, где можно получить несколькими клиентами. Укажите одно или несколько значений перечисления MSHLFLAGS.  
  
 `pSize`  
 После завершения этой операции представляет указатель на верхнюю границу объема данных для записи в поток маршалинга.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Значение S_OK, если успешно; в противном случае — значение E_FAIL или E_NOINTERFACE.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** ftm.h  
  
 **Пространство имен:** Microsoft::WRL  
  
## <a name="see-also"></a>См. также  
 [Класс FtmBase](../windows/ftmbase-class.md)