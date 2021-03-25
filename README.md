# PROYECTO1
La universidad está interesada en crear un sistema de información que le permita analizar los datos de los estudiantes matriculados.
//DECLARO LAS VARIABLES NECESARIAS
int cantEstu;

int codigoEstu [100];
int semestre [100];
float edad [100];
string sexo [100];
int estrato [100];
int codigoCar [100];
int descuento[100];
int total[100];
int i;
int sumaEdadHom, sumaEdadMuj;
float caso1, caso2, caso3, caso4, caso5, caso6;
int mujerMayor, hombreMenor;
float promeEdadHom, promeEdadMuj;

string user;
int password;



// DESARROLLO DE LA CLASE INTERFAZ
class interfaz{// LA CLASE INTERFAZ SIMULARA UN LOGIN
public:
	interfaz();
	void consejo();
	void usuario();
	void contra();
};


interfaz::interfaz(){//CONSTRUCTOR VACIO YA QUE NO HAY VARIAS QUE INICIALIZAR

}


void interfaz::consejo(){ // LE DAREMOS INDICACIONES EXPECIFICAS AL USUARIO DE COMO USAR EL PROGRAMA
	cout << "-----------------------------------------------------------------------------------------------" << endl;
	cout << "						| BIENVENIDO AL SISTEMA |" << endl;
	cout << "-----------------------------------------------------------------------------------------------" << endl;
	cout << "Antes de continuar tenga en cuenta los siguientes RECOMENDACIONES:" << endl;
	cout << " -El codigo del estudiantes es de 4 digitos." << endl;
	cout << " -El semestre va desde el numero 1 al 6"<< endl;
	cout << " -El sexo solo se responde con una F para femenino y M para masculino" << endl;
	cout << " -El estrato va desde el numero 1 al 6" << endl;
	cout << " -El valor del semestre es de $2.500.000, pero puede tener un descuento segun lo siguiente: " << endl;
	cout << "         | ESTRATO | DESCUENTO |" << endl;
	cout << "         |    1    |   90%     |" << endl;
	cout << "   	 |    2    |   70%     |" << endl;
	cout << "   	 |    3    |   50%     |" << endl;
	cout << "   	 |    4    |   30%     |" << endl;
	cout << "    	 |    5    |    0%     |" << endl;
	cout << " 	 |    6    |    0%     |" << endl;
	cout << " -Los codigos de la carrera son:" << endl;
	cout << "        | CODIGO |          CARRERA          |" << endl;
	cout << "	| 1001   |        sistemas           |" << endl;
	cout << "	| 1002   |        mecanica           |" << endl;
	cout << "	| 1003   |        mecatronica        |" << endl;
	cout << "	| 1004   | administracion de empresas|" << endl;
 	cout << " -Cada vez que se equivoque al ingresar un dato solo tendra 1 oportunidad mas" << endl;
	cout << "   para ingresar el dato correcto, de lo contrario" << endl;
	cout << "    EL SISTEMA SE BLOQUEARA POR SEGURIDAD" << endl;
	system ("pause");
	cout << endl;
	cout << "---------------------------LOGIN---------------------------" << endl;
}

void interfaz::usuario(){// LE PEDIMOS AL USUARIO QUE INGRESE EL USUARIO QUE ES ADMIN
	cout << "Digite el USUARIO: ";
	cin >> user; cout << endl;
}

void interfaz::contra(){// LE PEDIMOS AL USUARIO QUE INGRESE LA CONTRASEÑA QUE ES 12345
	cout << "Digite la CONTRASEÑA: ";
	cin >> password; cout << endl;
	cout << "----------------------------------------------------------------------------------------------------" << endl;
}



//DESARROLLO DE LA CLASE LEER
class leer{//LA CLASE LEER LE PEDIRA AL USUARIO EL INGRESO DE DATOS
public:
	leer();
	void cantEstudiante();
	void codigoEstudiante();
	void numeroSemestre();
	void edadEstudiante();
	void sexoEstudiante();
	void estratoEconomico();
	void codigoCarrera();
};


leer::leer(){//CONSTRUCTOR VACIO, NO HAY VARIABLES QUE INICIALIZAR
}


void leer::cantEstudiante(){//LE PEDIMOS AL USUARIO QUE INGRESE LA CANTIDAD DE ESTUDIANTES QUE REGISTRATA
	cout << "Ingrese el numero de estudiantes a ingresar: ";
	cin >> cantEstu;
	cout << endl;
}

void leer::codigoEstudiante(){//LE PEDIMOS AL USUARIO QUE INGRESE EL CODIGO DEL ESTUDIANTE
	cout << "Ingrese el codigo del estudiante #" << i << ": ";
	cin >> codigoEstu[i];
}

void leer::numeroSemestre(){//LE PEDIMOS AL USUARIO QUE INGRESE EL SEMESTRE QUE CURSA EL ESTUDIANTE
	cout << "Ingrese el semestre en el que se encuentra el estudiante #" << i << ": ";
	cin >> semestre[i];
}

void leer::edadEstudiante(){//LE PEDIMOS AL USUARIO QUE INGRESE LA EDAD DEL ESTUDIANTE
	cout << "Ingrese la edad del estudiante #" << i << ": ";
	cin >> edad[i];
}

void leer::sexoEstudiante(){//LE PEDIMOS AL USUARIO QUE INGRESE EL SEXO DEL ESTUDIANTE
	cout << "Ingrese el sexo del estudiante #" << i << ": ";
	cin >> sexo[i];
}

void leer::estratoEconomico(){//LE PEDIMOS AL USUARIO QUE INGRESE EL ESTRATO SOCIOECONOMICO DEL ESTUDIANTE
	cout << "Ingrese el estrato del estudiante #" << i << ": ";
	cin >> estrato[i];

}

void leer::codigoCarrera(){//LE PEDIMOS AL USUARIO QUE INGRESE EL CODIGO DE LA CARRERA QUE CURSA
	cout << "Ingrese el codigo de carrera en la que se encuentra el estudiante #" << i << ": ";
	cin >> codigoCar[i];
	cout << endl;

}


//DESARROLLO DE LA CLASE VALIDAR
class validar{//LA CLASE VALIDAR VALIDARA TODOS LOS DATOS INGRESADOS POR EL USUARIO
public:
	validar();
	bool validaUsuario();
	bool validaContra();
	bool validaCantEstu();
	bool validaCodigoEstu();
	bool validaSemestre();
	bool validaEdad();
	bool validaSexo();
	bool validaEstrato();
	bool validaCodigoCar();
};


validar::validar(){//CONSTRUCTOR VACIO, NO HAY VARIAS QUE INICIALIZAR

}


bool validar::validaUsuario(){//VALIDAMOS QUE EL USUARIO SEA CORRECTO, SI NO LO ES LE DAMOS UNA OPORTUNIDAD

	if(user=="ADMIN"){
		return true;
	}
	else{
		cout << "EL USUARIO INGRESADO ES INVALIDO | oportunidad restante 1 |" << endl;
		system("pause");
		interfaz usuarioNuevo;
		usuarioNuevo.usuario();
	}

}

bool validar::validaContra(){//VALIDAMOS QUE LA CONTRASEÑA SEA CORRECTA, SI NO LO ES LE DAMOS UNA OPORTUNIDAD
	if(password==12345){
		return true;
	}
	else{
		cout << "LA CONTRASEÑA INGRESADA ES INVALIDO | oportunidad restante 1 |" << endl;
		system("pause");
		interfaz contraNuevo;
		contraNuevo.contra();
	}
}

bool validar::validaCantEstu(){//VALIDAMOS QUE LA CANTIDAD DE ESTUDIANTES A INGRESAR ES MAYOR A 1, SI NO LO ES LE DAMOS UNA OPORTUNIDAD
	if(cantEstu>=1){
			return true;
		}
		else {
				cout << " La cantidad de estudiantes ingresa es INVALIDA| oportunidad restante 1 |" << endl;
				system ("pause");
				leer cantEstuNuevo;
				cantEstuNuevo.cantEstudiante();
			}
}

bool validar::validaCodigoEstu(){//VALIDAMOS QUE EL CODIGO DEL ESTUDIANTE TENGA 4 DIGITOS, SI NO LO ES LE DAMOS UNA OPORTUNIDAD
	if(codigoEstu[i]>=1000 && codigoEstu[i]<=9999){
		return true;
	}
	else {
			cout << " El codigo del estudiante es INVALIDO | oportunidad restante 1 |" << endl;
			system ("pause");
			leer codigoEstuNuevo;
			codigoEstuNuevo.codigoEstudiante();
	}
}

bool validar::validaSemestre(){//VALIDAMOS QUE EL SEMESTRE ESTE ENTRE 1 Y 6, SI NO LO ES LE DAMOS UNA OPORTUNIDAD
	if(semestre[i]>=1 && semestre[i]<=6){
		return true;
	}
	else {
		cout << " El semestre ingresado es INVALIDO | oportunidad restante 1 | " << endl;
		system("pause");
		leer semestreNuevo;
		semestreNuevo.numeroSemestre();
	}
}

bool validar::validaEdad(){//VALIDAMOS QUE LA EDAD SEA MAYOR O IGUAL A 16 SEGUN LA LEY COLOMBIANA, SI NO LO ES LE DAMOS UNA OPORTUNIDAD
	if(edad[i]>=16){
			return true;
		}
		else {
			cout << " La edad del estudiante es INVALIDO | oportunidad restante 1 | " << endl;
			system("pause");
			leer edadNueva;
			edadNueva.edadEstudiante();
		}
}

bool validar::validaSexo(){//VALIDAMOS QUE EL SEXO INGRESADO SEA CORRECTO, SI NO LO ES LE DAMOS UNA OPORTUNIDAD
	if(sexo[i]=="F" || sexo[i]=="M"){
		return true;

	}
	else {
		cout << " El sexo del estudiante es INVALIDO | oportunidad restante 1 | " << endl;
		system("pause");
		leer sexoNuevo;
		sexoNuevo.sexoEstudiante();
	}
}

bool validar::validaEstrato(){//VALIDAMOS QUE EL ESTRATO SOCIOECONOMICO ESTE ENTRE 1 Y 6, SI NO LO ES LE DAMOS UNA OPORTUNIDAD
	if(estrato[i]>=1 && estrato[i]<=6){
		return true;
	}
	else{
		cout << " El estrato ingresado es invalido | oportunidad restante 1 | " << endl;
		system ("pause");
		leer estratoNuevo;
		estratoNuevo.estratoEconomico();
	}
}

bool validar::validaCodigoCar(){//VALIDAMOS QUE EL CODIGO DE LA CARRERA INGRESADA SEA CORRECA, SI NO LO ES LE DAMOS UNA OPORTUNIDAD
	if(codigoCar[i]==1001 || codigoCar[i]==1002 || codigoCar[i]==1003 || codigoCar[i]==1004){
		return true;
	}
	else {
		cout << " El codigo de la carrera ingresado es invalido | oportunidad restante 1 | " << endl;
				system ("pause");
				leer codigoCarNuevo;
				codigoCarNuevo.codigoCarrera();
	}
}



//DESARROLLO DE LA CLASE CALCULAR
class calcular{//LA CLASE CALCULAR HARA LOS PROCEDIMIENTOS MATEMATICOS
public:
	calcular();
	void estudiantesXcarrera();
	void carMayorMatri();
	void carMenorMatri();
	void mujeresMayores();
	void hombresMenores();
	void promedioEdadMuj();
	void promedioEdadHom();
	void porcentajeDescuento();
	void valorPagar();
};


calcular::calcular(){//CONSTRUCTOR VACIO, NO HAY VARIABLES QUE INICIALIZAR

}


void calcular::estudiantesXcarrera(){//CONTAMOS CUANTOS ESTUDIANTES HAY POR CADA CARRERA
	for(i=1; i<=cantEstu; i++){
		if(codigoCar[i]==1001){
			caso1=caso1+1;
		}
		if(codigoCar[i]==1002){
			caso2=caso2+1;
		}
		if(codigoCar[i]==1003){
			caso3=caso3+1;
		}
		if(codigoCar[i]==1004){
			caso4=caso4+1;
		}
	}
}

void calcular::carMayorMatri(){//COMPARAMOS CUAL CARRERA TIENE UN MAYOR NUMERO DE ESTUDIANTES MATRICULADOS

	cout << "-------------------------------------------------------------------------------------" << endl;

	if (caso1>caso2 && caso1>caso3 && caso1>caso4){
		cout <<"La carrera con mayor estudiantes matriculados es la de Sistemas" << endl;
		}
	else if(caso2>caso1 && caso2>caso3 && caso2>caso4){
			cout << "La carrera con mayor estudiantes matriculados es la de Mecanica" << endl;
			}
	else if(caso3>caso1 && caso3>caso2 && caso3>caso4){
			cout << "La carrera con mayor estudiantes matriculados es la de Mecatronica" << endl;
			}
	else if(caso4>caso1 && caso4>caso2 && caso4>caso3){
			cout << "La carrera con mayor estudiantes matriculados es la de Administracion de empresas" << endl;
		}
	else{
			cout <<"No hay carreras con mayor numero de estudiantes matriculados"<< endl;
		}
}

void calcular::carMenorMatri(){//COMPARAMOS CUAL CARRERA TIENE UN MENOR NUMERO DE ESTUDIANTES MATRICULADOS

	if (caso1<caso2 && caso1<caso3 && caso1<caso4){
		cout <<"La carrera con menos estudiantes matriculados es la de Sistemas" << endl;
	}
	else if(caso2<caso1 && caso2<caso3 && caso2<caso4){
		cout << "La carrera con menos estudiantes matriculados es la de Mecanica" << endl;
		}
	else if(caso3<caso1 && caso3<caso2 && caso3<caso4){
			cout << "La carrera con menos estudiantes matriculados es la de Mecatronica" << endl;
			}
	else if(caso4<caso1 && caso4<caso2 && caso4<caso3){
			cout << "La carrera con menos estudiantes matriculados es la de Administracion de empresas"<< endl;
			}

		else{
			cout <<"No hay carreras con menor numero de estudiantes matriculados" << endl;
			}
	cout << endl;
}

void calcular::mujeresMayores(){//CALCULAMOS LA CANTIDAD DE MUJERES MAYORES A 18 AÑOS
	for(i=1; i<=cantEstu; i++){
		 if(sexo[i]=="F" && edad[i]>=18){
			 mujerMayor=mujerMayor+1;
		 }
	}
 }

void calcular::hombresMenores(){// CALCULAMOS LA CANTIDAD DE HOMBRES MENORES A 18 AÑOS

	for(i=1; i<=cantEstu; i++){
		 if(sexo[i]=="M" && edad[i]<18){
			 hombreMenor=hombreMenor+1;
		 }
	}
}

void calcular::promedioEdadHom(){//CALCULAMOS EL PROMEDIO DE LA EDAD EN LOS HOMBRES

	for(i=1; i<=cantEstu; i++){
		if(sexo[i]=="M"){
			caso5=caso5+1;
			sumaEdadHom=edad[i]+edad[i+1];
			promeEdadHom=sumaEdadHom/caso5;
		}
	}
}

void calcular::promedioEdadMuj(){//CALCULAMOS EL PROMEDIO DE LA EDAD EN LAS MUJERES

	for(i=1; i<=cantEstu; i++){
		if(sexo[i]=="F"){
			caso6=caso6+1;
			sumaEdadMuj=edad[i]+edad[i+1];
			promeEdadMuj=sumaEdadMuj/caso6;
		}
	}
}

void calcular::porcentajeDescuento(){//CALCULAMOS EL DESCUENTO SEGUN EL ESTRATO


	for(i=1; i<=cantEstu; i++){
		if (estrato[i]==1){
			descuento[i]=90*2500000/100;
		}
		else if  (estrato[i]==2){
			descuento[i]=70*2500000/100;
		}
		else if  (estrato[i]==3){
			descuento[i]=50*2500000/100;
		}
		else if  (estrato[i]==4){
			descuento[i]=30*2500000/100;
		}
	}
}

void calcular::valorPagar(){//CALCULAMOS EL TOTAL A PAGAR TENIENDO EN CUENTA EL DESCUENTO
	for(i=1; i<=cantEstu; i++){
		total[i]=2500000-descuento[i];
	}
}


//DESARROLLO DE LA CLASE RESULTADO
class resultado{//LA CLASE RESULTADO NOS MOSTRARA EL RESULTADO DE LAS OPERACIONES MATEMATICAS
public:
	resultado();
	    void mostrarEstudiantesXcarrera();
		void mostrarMayorMatri();
		void mostrarCarMenorMatri();
		void mostrarMujeresMayores();
		void mostrarHombresMenores();
		void mostrarPromedioEdadMuj();
		void mostrarPromedioEdadHom();
		void mostrarPorcentajeDescuento();
		void mostrarValorPagar();
};


resultado::resultado(){//CONSTRUCTOR VACIO, NO HAY VARIABLES QUE INICIALIZAR

}


void resultado::mostrarEstudiantesXcarrera(){//MOSTRAMOS LA CANTIDAD DE ESTUDIANTES MATRICULADOS EN CADA UNA DE LAS CARRERAS

	cout << "El numero de estudiantes matriculados en Sistemas es de: " << caso1 << endl;
	cout << "El numero de estudiantes matriculados en Mecanica es de: " << caso2 << endl;
    cout << "El numero de estudiantes matriculados en Mecatronica es de: " << caso3 << endl;
    cout << "El numero de estudiantes matriculados en Administracion de Empresas es de: " << caso4 << endl;
    cout << endl;
}

void resultado::mostrarMujeresMayores(){//MOSTRAMOS CUANTAS MUJERES SON MAYORES DE 18 AÑOS
	cout << "El total de mujeres mayores de edad es de: " << mujerMayor << endl;
}

void resultado::mostrarHombresMenores(){//MOSTRAMOS CUANTOS HOMBRES SON MENORES DE 18 AÑOS
	 cout << "El total de hombres menores de edad es de: " << hombreMenor << endl;
	 cout << endl;
}

void resultado::mostrarPromedioEdadHom(){//MOSTRAMOS EL PROMEDIO DE LA EDAD EN LOS HOMBRES
	cout << "El promedio de edad de los estudiantes hombres es de: " << promeEdadHom << endl;
	cout << endl;
}

void resultado::mostrarPromedioEdadMuj(){//MOSTRAMOS EL PROMEDIO DE LA EDAD DE LAS MUJERES
	cout << "El promedio de edad de los estudiantes mujeres es de: " << promeEdadMuj << endl;

}

void resultado::mostrarPorcentajeDescuento(){//MOSTRAMOS EL DESCUENTO QUE TENDRA CADA ESTUDIANTE

	for(i=1; i<=cantEstu; i++){
	cout << "El estudiante #" << i << " tendra un descuento de: $" << descuento[i] << "segun la tabla del estrato"<< endl;
	}
	cout << endl;
}

void resultado::mostrarValorPagar(){//MOSTRAMOS EL VALOR TOTAL A PAGAR DE CADA ESTUDIANTE
	for(i=1; i<=cantEstu; i++){
	cout << "El estudiante #" << i << " pagara $" << total[i] << endl;
	}
}


//DESARROLLO DE LA CLASE MOSTRARCLASES
class mostrarClases{//LA CLASE MOSTRARCLASES DONDE LLAMAREMOS LOS OBJETOS Y LAS CLASES QUE USAREMOS
public:
	mostrarClases();
	void mostrarClass();
};


mostrarClases::mostrarClases(){//CONSTRUCTO VACIO, NO HAY VARIAS QUE INICIALIZAR

}


void mostrarClases::mostrarClass(){//CREAMOS LOS OBJETOS DE CADA CLASE EN EL ORDEN QUE QUEREMOS QUE FUNCIONE

	    interfaz interfaz1;
		leer leer1;
		validar validar1;
		calcular calcular1;
		resultado resultado1;

		interfaz1.consejo();

		interfaz1.usuario();
		validar1.validaUsuario();

		interfaz1.contra();
		validar1.validaContra();

		leer1.cantEstudiante();
		validar1.validaCantEstu();

	for(i=1; i<=cantEstu; i++){
		leer1.codigoEstudiante();
		validar1.validaCodigoEstu();

		leer1.numeroSemestre();
		validar1.validaSemestre();

		leer1.edadEstudiante();
		validar1.validaEdad();

		leer1.sexoEstudiante();
		validar1.validaSexo();

		leer1.estratoEconomico();
		validar1.validaEstrato();

		leer1.codigoCarrera();
		validar1.validaCodigoCar();
	}

		calcular1.estudiantesXcarrera();
		calcular1.carMayorMatri();
		calcular1.carMenorMatri();
		calcular1.mujeresMayores();
		calcular1.hombresMenores();
		calcular1.promedioEdadHom();
		calcular1.promedioEdadMuj();


		resultado1.mostrarEstudiantesXcarrera();
		resultado1.mostrarMujeresMayores();
		resultado1.mostrarHombresMenores();
		resultado1.mostrarPromedioEdadMuj();
		resultado1.mostrarPromedioEdadHom();

		calcular1.porcentajeDescuento();
		resultado1.mostrarPorcentajeDescuento();
		calcular1.valorPagar();
		resultado1.mostrarValorPagar();


}


//DESARROLLO DEL INT MAIN
int main() {

mostrarClases mostrarClases1;//CREAMOS EL OBJETO DE LA CLASE QUE CONTIENE EL LLAMADO DE LAS DEMAS CLASES
mostrarClases1.mostrarClass();

	return 0;
}
