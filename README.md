import random
from datetime import datetime
def verificar_patente(patente):
    vocales='AEIOU'
    if len(patente) !=6:
        return 0
    if patente[:4].isalpha()and patente[4:].isdigit()and not any (v in patente[:4].upper()for v in vocales):
        return 1
    if patente[:2].isalpha()and patente[2:].isdigit()and not any (v in patente[:2].upper()for v in vocales):
        return 1
    return 0
def grabar(datos,multas):
    registro=[]
    registro.append(datos['tipo'])
    registro.append(datos['patente'].upper())
    registro.append(datos['marca'])
    registro.append(datos['precio'])
    registro.append(datos['dueño'])
    registro.append(datos['fecha'])
    registro.append(multas)
    registro.append(random.rendint(1500,3500))
    registro.append(random.rendint(1500,3500))
    return registro
def buscar(patente,registro):
    patente=patente.upper()
    lili=0
    cont=1
    for x in registro:
        if patente==x[1]:
            lili=1
            print('\ntipo:',x[0])
            print('\npatente:',x[1])
            print('\nmarca:',x[2])
            print('\nprecio:',x[3])
            print('\ndueño:',x[4])
            print('\nfecha:',x[5])
            if len(x[6])==0:
                print('no se encotraron multas.')
            elif len (x[6])==1:
                print('se encotro 1 multa.')
            else:
                print('\nse encotraron',len(x[6]),'multas')
            for multa in[6]:
                if len(multa)>0:
                    print('\nmulta:',cont)
                    print('\tmonto:',[0])
                    print('\tfecha:',[1])
                    cont+=1
    if lili==0:
        print('\nNo se encotraron registros')
        return 0
def certificados(patente,registro):
    patente=patente=upper()
    lili=0
    cont=1
    for x in registro:
        if patente==x[1]:
            lili=1
            print('\n')
            print('__________________')
            print('certificado de emision de contaminantes')
            print('patente:',x[1])
            print('dueño',x[4])
            print('valor',x[7])
            print('    APROBADO      ')
            print('__________________')
            print('\n')
            print('__________________')
            print('certificado de anotaciones vigentes')
            print('patente',x[1])
            print('dueño',x[4])
            print('valor',x[8])
            print('    APROBADO      ')
            print('__________________')
            if len(x[6])==0:
                print('\nno encotron multas.')
            elif len(x[6])==1:
                print('\nse encotro 1 multa')
            else:
                print('\nse encotraron',len([6]),'multas')
            for multa in x[6]:
                if len(multa)>0:
                    print('\nmulta',cont)
                    print('\tmonto',multa[0])
                    print('\tfecha:',[1])
                    cont+=1
    if lili==0:
        print('\nno se encotraron registros')
        return 0
    registro=[]
    menu=0
    while menu!=4:
        print('\n1 grabar')
        print('\n1 buscar')
        print('\n1 imprimir certificador')
        print('\n1 salir')
        menu=int(input('\nescoja una alternativa'))
        if menu<1 or meru>4:
            print('\nopcion invalida')
        if menu==1:
            datos={'tipo':'x','marca':'x','precio':0,'dueño':'x','fecha':'x'}
            multas=[]
            pat=0
            datos['tipo']=input('ingrese tipo de vehiculo')
            while pat==0:
                datos['patente']=input('ingrese patetente del vehiculo')
                pat=verificar_patente(datps['patente'])
                if pat==0:
                    print('patente invalida')
            while len (datos['marca'])<2 or len (datos['marca'])>15:
                datos['marca']=input('ingrese marca de vehiculo')
                if len (datos['marca'])<2 or len (datos['marca'])>15:
                    print('la marca debe de tener entre 2 a 15 caracteres')
            while datos ['precio']<5000000:
                datos['precio']=input('ingrese precio del vehiculo')
                if datos['precio']<5000000:
                    print('el precio debe ser mas a $5000000')
            datos['dueño']=input('ingrese nombre del dueño')
            while True:
                datos['fecha']=input('ingrese fecha de registro de vehiculo(aaa/mm/dd): ')
                try:
                    fecha=datetime.strtime(datos['fecha'],'%Y-%m-%d').strtime('%d-%m-%Y')
                    print('\nla fecha del registro es')
                    print(str(fecha))
                except ValueError:
                    print('\nNo a ingresado la fecha correcta...\n')
                else:
                    break
            mult=int(input('\ntiene multas?:\n1si.\n2.\n'))
            while mult==1:
                multas2=[]
                multas2.append(int(input('ingrese el monto de la multa')))
                while True:
                    multas2.append(input('ingrese el monto de la multa(aaa/mm/dd):'))
                    try:
                        fecha=datetime.strtime(datos['fecha'],'%Y-%m-%d').strtime('%d-%m-%Y')
                        print('\nla fecha de la multa es')
                        print(str(fecha))
                    except ValueError:
                        print('\nno a ingresado la fecha correcta')
                        break


