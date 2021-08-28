# for nRF5_SDK module compiling
Import('rtconfig')
from building import *

cwd  = GetCurrentDir()
src = Glob('./drivers/src/*.c')
path = []
define = []

#include
path += [cwd]
path += [cwd + '/drivers']
path += [cwd + '/drivers/include']
path += [cwd + '/mdk']
path += [cwd + '/hal']

#chip toolchain
if GetDepend('SOC_NRF52840') == True:
	define += ['NRF52840_XXAA']
	src += ['./mdk/system_nrf52840.c']
	
	if rtconfig.PLATFORM == 'armcc':
		src += ['./mdk/arm_startup_nrf52840.s']
		
	if rtconfig.PLATFORM == 'gcc':
		src += ['./mdk/gcc_startup_nrf52840.S']
		
	if rtconfig.PLATFORM == 'iar':
		D_SRC += ['./mdk/iar_startup_nrf52840.s']

elif GetDepend('SOC_NRF52833') == True:
	define += ['NRF52833_XXAA']
	src += ['./mdk/system_nrf52833.c']
	
	if rtconfig.PLATFORM == 'armcc':
		src += ['./mdk/arm_startup_nrf52833.s']
		
	if rtconfig.PLATFORM == 'gcc':
		src += ['./mdk/gcc_startup_nrf52833.S']
		
	if rtconfig.PLATFORM == 'iar':
		D_SRC += ['./mdk/iar_startup_nrf52833.s']

elif GetDepend('SOC_NRF52832') == True:
	define += ['NRF52832_XXAA']
	src += ['./mdk/system_nrf52.c']
	
	if rtconfig.PLATFORM == 'armcc':
		src += ['./mdk/arm_startup_nrf52.s']
		
	if rtconfig.PLATFORM == 'gcc':
		src += ['./mdk/gcc_startup_nrf52.S']
		
	if rtconfig.PLATFORM == 'iar':
		D_SRC += ['./mdk/iar_startup_nrf52.s']
        
        
elif GetDepend('SOC_NRF51822') == True:
	define += ['NRF51822_XXAA']
	src += ['./mdk/system_nrf51.c']
	
	if rtconfig.PLATFORM == 'armcc':
		src += ['./mdk/arm_startup_nrf51.s']
		
	if rtconfig.PLATFORM == 'gcc':
		src += ['./mdk/gcc_startup_nrf51.S']
		
	if rtconfig.PLATFORM == 'iar':
		D_SRC += ['./mdk/iar_startup_nrf51.s']
else:
	pass
#group
group = DefineGroup('nrf_Drivers', src, depend = [''], CPPPATH = path, CPPDEFINES = define)

Return('group')

