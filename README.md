# limpar-area-transferencia
Limpar área de transferência
private void showStatusItem_Click(object sender, EventArgs e)
{
    ShowStatusView();
}

private void ShowStatusView()
{
    if (_statusView == null)
    {
        _statusView = new WpfFormLibrary.View.StatusView();
        _statusView.DataContext = _statusViewModel;

        _statusView.Closing += ((arg_1, arg_2) => _statusView = null);
        _statusView.WindowStartupLocation = System.Windows.WindowStartupLocation.CenterScreen;
        _statusView.Show();
        UpdateStatusView();
    }
    else
    {
        _statusView.Activate();
    }
    _statusView.Icon = AppIcon;
}
