CREATE DATABASE RECUPERACION;

-- tables
-- Table: COMPRA
CREATE TABLE COMPRA (
    CODCOM char(5)  NOT NULL,
    FECCOM datetime  NOT NULL,
    CODVEND char(4)  NOT NULL,
    CODPROV char(5)  NOT NULL,
    ESTCOM char(1)  NOT NULL,
    Vendedor_CODVEND char(4)  NOT NULL,
    PROVEEDOR_CODPROV char(5)  NOT NULL,
    CONSTRAINT COMPRA_pk PRIMARY KEY (CODCOM)
);

-- Table: COMPRADETALLE
CREATE TABLE COMPRADETALLE (
    IDCOMDET int  NOT NULL,
    CODCOM char(5)  NOT NULL,
    CODPRO char(5)  NOT NULL,
    CANRPRO int  NOT NULL,
    Producto_CODPRO char(5)  NOT NULL,
    COMPRA_CODCOM char(5)  NOT NULL,
    CONSTRAINT COMPRADETALLE_pk PRIMARY KEY (IDCOMDET)
);

-- Table: Cliente
CREATE TABLE Cliente (
    CODCLI char(4)  NOT NULL COMMENT 'CODIGO DEL CLINETE',
    NOMCLI varchar(60)  NOT NULL COMMENT 'NOMBRE DEL CLIENTE',
    APECLIC varchar(60)  NOT NULL COMMENT 'APELLIDO DEL CLIENTE',
    EMACLI varchar(60)  NOT NULL COMMENT 'EMAIL DEL CLIENTE',
    CELCLI char(9)  NOT NULL COMMENT 'CELULAR DELO CLIENTE',
    DIRCLI varchar(70)  NOT NULL COMMENT 'DIRECCION  DEL CLIENTE',
    ESTCLI char(1)  NOT NULL COMMENT 'ESTADO DEL CLIENTE A(activo) I(inactivo)',
    CONSTRAINT Cliente_pk PRIMARY KEY (CODCLI)
);

-- Table: PROVEEDOR
CREATE TABLE PROVEEDOR (
    CODPROV char(5)  NOT NULL,
    RAZSOCPROV varchar(90)  NOT NULL,
    RUCPROV varchar(11)  NOT NULL,
    EMAPROV varchar(60)  NOT NULL,
    ESTPROV char(1)  NOT NULL,
    CONSTRAINT PROVEEDOR_pk PRIMARY KEY (CODPROV)
);

-- Table: Producto
CREATE TABLE Producto (
    CODPRO char(5)  NOT NULL,
    DESCPRO varchar(60)  NOT NULL,
    CATPRO char(1)  NOT NULL,
    PREPRO decimal(8,2)  NOT NULL,
    STOPKPRO int  NOT NULL,
    ESTPRO char(1)  NOT NULL,
    CONSTRAINT Producto_pk PRIMARY KEY (CODPRO)
);

-- Table: VENTA
CREATE TABLE VENTA (
    CODVEN char(5)  NOT NULL,
    FECVEN datetime  NOT NULL,
    CODCLI char(4)  NOT NULL,
    CODVEND char(4)  NOT NULL,
    ESTVEN char(1)  NOT NULL,
    Cliente_CODCLI char(4)  NOT NULL,
    Vendedor_CODVEND char(4)  NOT NULL,
    CONSTRAINT VENTA_pk PRIMARY KEY (CODVEN)
);

-- Table: VENTADETALLE
CREATE TABLE VENTADETALLE (
    IDVENDET int  NOT NULL,
    CODVEN char(5)  NOT NULL,
    CODPRO char(5)  NOT NULL,
    CANTPRO int  NOT NULL,
    VENTA_CODVEN char(5)  NOT NULL,
    CONSTRAINT VENTADETALLE_pk PRIMARY KEY (IDVENDET)
);

-- Table: Vendedor
CREATE TABLE Vendedor (
    CODVEND char(4)  NOT NULL,
    NOMVEND varchar(60)  NOT NULL,
    APEVEND varchar(60)  NOT NULL,
    EMAVEND varchar(60)  NOT NULL,
    CELVEND char(9)  NOT NULL,
    DIRVEND varchar(60)  NOT NULL,
    ESTVEND char(1)  NOT NULL,
    CONSTRAINT Vendedor_pk PRIMARY KEY (CODVEND)
);

-- foreign keys
-- Reference: COMPRADETALLE_COMPRA (table: COMPRADETALLE)
ALTER TABLE COMPRADETALLE ADD CONSTRAINT COMPRADETALLE_COMPRA FOREIGN KEY COMPRADETALLE_COMPRA (COMPRA_CODCOM)
    REFERENCES COMPRA (CODCOM);

-- Reference: COMPRADETALLE_Producto (table: COMPRADETALLE)
ALTER TABLE COMPRADETALLE ADD CONSTRAINT COMPRADETALLE_Producto FOREIGN KEY COMPRADETALLE_Producto (Producto_CODPRO)
    REFERENCES Producto (CODPRO);

-- Reference: COMPRA_PROVEEDOR (table: COMPRA)
ALTER TABLE COMPRA ADD CONSTRAINT COMPRA_PROVEEDOR FOREIGN KEY COMPRA_PROVEEDOR (PROVEEDOR_CODPROV)
    REFERENCES PROVEEDOR (CODPROV);

-- Reference: COMPRA_Vendedor (table: COMPRA)
ALTER TABLE COMPRA ADD CONSTRAINT COMPRA_Vendedor FOREIGN KEY COMPRA_Vendedor (Vendedor_CODVEND)
    REFERENCES Vendedor (CODVEND);

-- Reference: VENTADETALLE_VENTA (table: VENTADETALLE)
ALTER TABLE VENTADETALLE ADD CONSTRAINT VENTADETALLE_VENTA FOREIGN KEY VENTADETALLE_VENTA (VENTA_CODVEN)
    REFERENCES VENTA (CODVEN);

-- Reference: VENTA_Cliente (table: VENTA)
ALTER TABLE VENTA ADD CONSTRAINT VENTA_Cliente FOREIGN KEY VENTA_Cliente (Cliente_CODCLI)
    REFERENCES Cliente (CODCLI);

-- Reference: VENTA_Vendedor (table: VENTA)
ALTER TABLE VENTA ADD CONSTRAINT VENTA_Vendedor FOREIGN KEY VENTA_Vendedor (Vendedor_CODVEND)
    REFERENCES Vendedor (CODVEND);

-- End of file.


insert into cliente
( CODCLI , NOMCLI, APECLIC , EMACLI ,CELCLI ,DIRCLI ,ESTCLI )
values
('CLO1','Juana','Campos Ortiz','juana.campos@gmail.com','987485152','Av.Miraflores','A'),
('CLO2','Sofia','Barrios Salcedo','sofia.barrios@outlook.com','','jr. Huallaga','A'),
('CLO3','Claudio','perez luna','claudio.perez@outlook.com','984512147','Av.Libertadores','A'),
('CLO4','Marcos','Avila Manco','marcos.avila@yahoo.com','','Calle Huallaga','A'),
('CLO5','Anastasio','salomon Inti','anastasio.salomon@gmail.com','','Av.San Martin','A');




insert into vendedor
  ( CODVEND ,NOMVEND,APEVEND, EMAVEND ,CELVEND , DIRVEND , ESTVEND)
values
('VEN1','Gloria','Carrizales Paredes','gloria.carrizales@gmail.com','984574123','Calle Las Begonias','A'),
('VEN2','Gabriel','Lozada Lombardi','gabriel.lozada@gmail.com','974512368','AV.Los Girasoles','A'),
('VEN3','Gilberto','Carrizales Paredes','gilberto.martinez@gmail.com','','Jr.San Martin','A');

insert into proveedor
  (  CODPROV ,
    RAZSOCPROV ,
    RUCPROV ,
    EMAPROV ,
    ESTPROV )
values
('PRV01','LG Coportation','87542136951','informes@Ig.com.pe','A'),
('PRV02','SONY','45213698741','informes@sony.com.pe','A'),
('PRV03','SAMSUNG','85321697661','informes@samsung.com.pe','A'),
('PRV04','OSTER SRL','55663214478','informes@oster.com.pe','A'),
('PRV05','ASUS','99663325478','informes@asus.com.pe','A');

insert into producto
  ( CODPRO , DESCPRO ,CATPRO ,PREPRO ,STOPKPRO ,ESTPRO  )
values
('PRO01','Refrigedora LG Side By Side','1','4149','15','A'),
('PRO02','Refrigedora SBS 602L','1','3599','10','A'),
('PRO03','Refrigedora Top Mount 500 L','1','2799','8','A'),
('PRO04','TV SAMSUNG UHD 55"','2','1799','25','A'),
('PRO05','Televisor 65"LG UHD 4K','2','2999','20','A'),
('PRO06','TV CRYSTAL UHD 55','2','2299','7','A'),
('PRO07','ASUS X415JA Core i3 10a Gen 14"','3','1099','17','A'),
('PRO08','Lenovo IdeaPad 5i Intel Core i7 14','3','3099','10','A'),
('PRO09','Laptop HP 15-dw1085laIntel Core i3','3','1600','15','A'),
('PRO10','Galaxy A52 128GB','4','1200','25','A'),
('PRO11','iPhone 11 64GB Morado','4','2600','30','A'),
('PRO12','Poco X3 GT 5G 256GB 8GB','4','1450','20','A');

