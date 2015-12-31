unit Unit1;

interface

uses
  Windows, Messages, SysUtils, Variants, Classes, Graphics, Controls, Forms,
  Dialogs, StdCtrls, DB, ADODB, Grids, DBGrids;

type
  TForm1 = class(TForm)
    DataSource1: TDataSource;
    DBGrid1: TDBGrid;
    ADOConnection1: TADOConnection;
    ADOTable1: TADOTable;
    Label1: TLabel;
    NameVal: TLabel;
    Label3: TLabel;
    MarkVal: TLabel;
    Label5: TLabel;
    DateVal: TLabel;
    Label7: TLabel;
    PowerVal: TLabel;
    NameSrc: TEdit;
    Label9: TLabel;
    MarkSrc: TEdit;
    Label10: TLabel;
    PowerSrc: TEdit;
    Label11: TLabel;
    DateSrc: TEdit;
    Label12: TLabel;
    Button1: TButton;
    Button2: TButton;
    Button3: TButton;
    procedure Button1Click(Sender: TObject);
    procedure Button2Click(Sender: TObject);
    procedure Button3Click(Sender: TObject);
    procedure DBGrid1CellClick(Column: TColumn);
  private
    { Private declarations }
  public
    procedure RefreshInfo();
    { Public declarations }
  end;

var
  Form1: TForm1;

implementation

{$R *.dfm}

procedure TForm1.RefreshInfo();
begin
  NameVal.Caption := ADOTable1.FieldByName('t_NAME').AsString;
  MarkVal.Caption := ADOTable1.FieldByName('t_MARK').AsString;
  PowerVal.Caption := ADOTable1.FieldByName('t_MARK').AsString;
  DateVal.Caption := ADOTable1.FieldByName('t_DATE').AsString;
end;

procedure TForm1.Button1Click(Sender: TObject);
begin
  ADOTable1.Edit;
  ADOTable1.Insert;
  ADOTable1.FieldByName('t_NAME').AsString := NameSrc.Text;
  ADOTable1.FieldByName('t_MARK').AsString := MarkSrc.Text;
  ADOTable1.FieldByName('t_POWER').AsString := PowerSrc.Text;
  ADOTable1.FieldByName('t_DATE').AsString := DateSrc.Text;
  ADOTable1.Edit;
  ADOTable1.Post;
end;

procedure TForm1.Button2Click(Sender: TObject);
begin
  ADOTable1.Edit;
  ADOTable1.FieldByName('t_NAME').AsString := NameSrc.Text;
  ADOTable1.FieldByName('t_MARK').AsString := MarkSrc.Text;
  ADOTable1.FieldByName('t_POWER').AsString := PowerSrc.Text;
  ADOTable1.FieldByName('t_DATE').AsString := DateSrc.Text;
  ADOTable1.Edit;
  ADOTable1.Post;
end;

procedure TForm1.Button3Click(Sender: TObject);
begin

  if (ADOTable1.RecordCount < 2) then
  begin
   Exit;
  end;

  ADOTable1.Edit;
  ADOTable1.Delete;
  ADOTable1.Edit;
  ADOTable1.Post;
end;

procedure TForm1.DBGrid1CellClick(Column: TColumn);
begin
  RefreshInfo;
end;

end.
