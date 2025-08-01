@override
  Widget build(BuildContext context) {
    return Scaffold(
      appBar: AppBar(title: Text('智能遥控器')),
      body: GridView.count(
        crossAxisCount: 3,
        children: [
          _buildButton('电源', Icons.power_settings_new, () {
            controller.sendCommand('power');
          }),
          _buildButton('音量+', Icons.volume_up, () {
            controller.sendCommand('volume_up');
          }),
          _buildButton('音量-', Icons.volume_down, () {
            controller.sendCommand('volume_down');
          }),
          // 添加更多按钮...
        ],
      ),
    );
  }
  
  Widget _buildButton(String label, IconData icon, VoidCallback onPressed) {
    return Padding(
      padding: const EdgeInsets.all(8.0),
      child: ElevatedButton(
        style: ElevatedButton.styleFrom(
          minimumSize: Size(100, 100),
        ),
        onPressed: onPressed,
        child: Column(
          mainAxisAlignment: MainAxisAlignment.center,
          children: [
            Icon(icon, size: 40),
            Text(label),
          ],
        ),
      ),
    );
  }
}
