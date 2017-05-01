public boolean onCommand(CommandSender sender, org.bukkit.command.Command cmd, String label, String[] args) {
		Player p = (Player)sender;
		if(cmd.getName().equalsIgnoreCase("Particle")){
    if(args.length == 1){
			if(args[0].equalsIgnoreCase("Hearts")){
		Location l = p.getLocation();
    // This will create a Helius
    double radius = 2;
		double maxheight = 8;
		for(double y1  = 0; y1 <maxheight; y1+= 0.08){
			 double x1 = Math.cos(y1*radius);
			 double z1 = Math.sin(y1*radius);
			 PacketPlayOutWorldParticles particle1 = new PacketPlayOutWorldParticles(EnumParticle.HEART, true, ((float)(l.getX() + x1)),                ((float)(l.getY() + y1)), ((float)(l.getZ() + z1)), 0, 0, 0, 1, 0);
				
				PlayerConnection connection1 = ((CraftPlayer)p).getHandle().playerConnection;
				connection1.sendPacket(particle1);
